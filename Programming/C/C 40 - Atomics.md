# 40 Atomics

> _“They tried and failed, all of them?”_  
> _“Oh, no.” She shook her head. “They tried and died.”_
> 
> —Paul Atreides and The Reverend Mother Gaius Helen Mohiam, _Dune_

This is one of the more challenging aspects of multithreading with C. But we’ll try to take it easy.

Basically, I’ll talk about the more straightforward uses of atomic variables, what they are, and how they work, etc. And I’ll mention some of the more insanely-complex paths that are available to you.

But I won’t go down those paths. Not only am I barely qualified to even write about them, but I figure if you know you need them, you already know more than I do.

But there are some weird things out here even in the basics. So buckle your seatbelts, everyone, ‘cause Kansas is goin’ bye-bye.



## 40.1 Testing for Atomic Support

Atomics are an optional feature. There’s a macro `__STDC_NO_ATOMICS__` that’s `1` if you _don’t_ have atomics.

That macro might not exist pre-C11, so we should test the language version with `__STDC_VERSION__`[195](https://beej.us/guide/bgc/html/split/footnotes.html#fn195).

```
#if __STDC_VERSION__ < 201112L || __STDC_NO_ATOMICS__ == 1
#define HAS_ATOMICS 0
#else
#define HAS_ATOMICS 1
#endif
```

If those tests pass, then you can safely include `<stdatomic.h>`, the header on which the rest of this chapter is based. But if there is no atomic support, that header might not even exist.

On some systems, you might need to add `-latomic` to the end of your compilation command line to use any functions in the header file.

## 40.2 Atomic Variables

Here’s _part_ of how atomic variables work:

If you have a shared atomic variable and you write to it from one thread, that write will be _all-or-nothing_ in a different thread.

That is, the other thread will see the entire write of, say, a 32-bit value. Not half of it. There’s no way for one thread to interrupt another that is in the _middle_ of an atomic multi-byte write.

It’s almost like there’s a little lock around the getting and setting of that one variable. (And there _might_ be! See [Lock-Free Atomic Variables](https://beej.us/guide/bgc/html/split/chapter-atomics.html#lock-free-atomic), below.)

And on that note, you can get away with never using atomics if you use mutexes to lock your critical sections. It’s just that there are a class of _lock-free data structures_ that always allow other threads to make progress instead of being blocked by a mutex… but these are tough to create correctly from scratch, and are one of the things that are beyond the scope of the guide, sadly.

That’s only part of the story. But it’s the part we’ll start with.

Before we go further, how do you declare a variable to be atomic?

First, include `<stdatomic.h>`.

This gives us types such as `atomic_int`.

And then we can simply declare variables to be of that type.

But let’s do a demo where we have two threads. The first runs for a while and then sets a variable to a specific value, then exits. The other runs until it sees that value get set, and then it exits.

```
#include <stdio.h>
#include <threads.h>
#include <stdatomic.h>

atomic_int x;   // THE POWER OF ATOMICS! BWHAHAHA!

int thread1(void *arg)
{
    (void)arg;

    printf("Thread 1: Sleeping for 1.5 seconds\n");
    thrd_sleep(&(struct timespec){.tv_sec=1, .tv_nsec=500000000}, NULL);

    printf("Thread 1: Setting x to 3490\n");
    x = 3490;

    printf("Thread 1: Exiting\n");
    return 0;
}

int thread2(void *arg)
{
    (void)arg;

    printf("Thread 2: Waiting for 3490\n");
    while (x != 3490) {}  // spin here

    printf("Thread 2: Got 3490--exiting!\n");
    return 0;
}

int main(void)
{
    x = 0;

    thrd_t t1, t2;

    thrd_create(&t1, thread1, NULL);
    thrd_create(&t2, thread2, NULL);

    thrd_join(t1, NULL);
    thrd_join(t2, NULL);

    printf("Main    : Threads are done, so x better be 3490\n");
    printf("Main    : And indeed, x == %d\n", x);
}
```

The second thread spins in place, looking at the flag and waiting for it to get set to the value `3490`. And the first one does that.

And I get this output:

```
Thread 1: Sleeping for 1.5 seconds
Thread 2: Waiting for 3490
Thread 1: Setting x to 3490
Thread 1: Exiting
Thread 2: Got 3490--exiting!
Main    : Threads are done, so x better be 3490
Main    : And indeed, x == 3490
```

Look, ma! We’re accessing a variable from different threads and not using a mutex! And that’ll work every time thanks to the atomic nature of atomic variables.

You might be wondering what happens if that’s a regular non-atomic `int`, instead. Well, on my system it still works… unless I do an optimized build in which case it hangs on thread 2 waiting to see the 3490 to get set[196](https://beej.us/guide/bgc/html/split/footnotes.html#fn196).

But that’s just the beginning of the story. The next part is going to require more brain power and has to do with something called _synchronization_.

## 40.3 Synchronization

The next part of our story is all about when certain memory writes in one thread become visible to those in another thread.

You might think, it’s right away, right? But it’s not. A number of things can go wrong. Weirdly wrong.

The compiler might have rearranged memory accesses so that when you think you set a value relative to another might not be true. And even if the compiler didn’t, your CPU might have done it on the fly. Or maybe there’s something else about this architecture that causes writes on one CPU to be delayed before they’re visible on another.

The good news is that we can condense all these potential troubles into one: unsynchronized memory accesses can appear out of order depending on which thread is doing the observing, as if the lines of code themselves had been rearranged.

By way of example, which happens first in the following code, the write to `x` or the write to `y`?

```
int x, y;  // global

// ...

x = 2;
y = 3;

printf("%d %d\n", x, y);
```

Answer: we don’t know. The compiler or CPU could silently reverse lines 5 and 6 and we’d be none-the-wiser. The code would run single-threaded _as-if_ it were executed in code order.

In a multithreaded scenario, we might have something like this pseudocode:

```
int x = 0, y = 0;

thread1() {
    x = 2;
    y = 3;
}

thread2() {
    while (y != 3) {}  // spin
    printf("x is now %d\n", x);  // 2? ...or 0?
}
```

What is the output from thread 2?

Well, if `x` gets assigned `2` _before_ `y` is assigned `3`, then I’d expect the output to be the very sensible:

```
x is now 2 
```

But something sneaky could rearrange lines 4 and 5 causing us to see the value of `0` for `x` when we print it.

In other words, all bets are off unless we can somehow say, “As of this point, I expect all previous writes in another thread to be visible in this thread.”

Two threads _synchronize_ when they agree on the state of shared memory. As we’ve seen, they’re not always in agreement with the code. So how do they agree?

Using atomic variables can force the agreement[197](https://beej.us/guide/bgc/html/split/footnotes.html#fn197). If a thread writes to an atomic variable, it’s saying “anyone who reads this atomic variable in the future will also see all the changes I made to memory (atomic or not) up to and including the atomic variable”.

Or, in more human terms, let’s sit around the conference table and make sure we’re on the same page as to which pieces of shared memory hold what values. You agree that the memory changes that you’d made up-to-and-including the atomic store will be visible to me after I do a load of the same atomic variable.

So we can easily fix our example:

```
int x = 0;
atomic int y = 0;  // Make y atomic

thread1() {
    x = 2;
    y = 3;             // Synchronize on write
}

thread2() {
    while (y != 3) {}  // Synchronize on read
    printf("x is now %d\n", x);  // 2, period.
}
```

Because the threads synchronize across `y`, all writes in thread 1 that happened _before_ the write to `y` are visible in thread 2 _after_ the read from `y` (in the `while` loop).

It’s important to note a couple things here:

1. Nothing sleeps. The synchronization is not a blocking operation. Both threads are running full bore until they exit. Even the one stuck in the spin loop isn’t blocking anyone else from running.
    
2. The synchronization happens when one thread reads an atomic variable another thread wrote. So when thread 2 reads `y`, all previous memory writes in thread 1 (namely setting `x`) will be visible in thread 2.
    
3. Notice that `x` isn’t atomic. That’s OK because we’re not synchronizing over `x`, and the synchronization over `y` when we write it in thread 1 means that all previous writes—including `x`—in thread 1 will become visible to other threads… if those other threads read `y` to synchronize.
    

Forcing this synchronization is inefficient and can be a lot slower than just using a regular variable. This is why we don’t use atomics unless we have to for a particular application.

So that’s the basics. Let’s look deeper.

## 40.4 Acquire and Release

More terminology! It’ll pay off to learn this now.

When a thread reads an atomic variable, it is said to be an _acquire_ operation.

When a thread writes an atomic variable, it is said to be a _release_ operation.

What are these? Let’s line them up with terms you already know when it comes to atomic variables:

**Read = Load = Acquire**. Like when you compare an atomic variable or read it to copy it to another value.

**Write = Store = Release**. Like when you assign a value into an atomic variable.

When using atomic variables with these acquire/release semantics, C spells out what can happen when.

Acquire/release form the basis for the synchronization we just talked about.

When a thread acquires an atomic variable, it can see values set in another thread that released that same variable.

In other words:

When a thread reads an atomic variable, it can see values set in another thread that wrote to that same variable.

The synchronization happens across the acquire/release pair.

More details:

With read/load/acquire of a particular atomic variable:

- All writes (atomic or non-atomic) in another thread that happened before that other thread wrote/stored/released this atomic variable are now visible in this thread.
    
- The new value of the atomic variable set by the other thread is also visible in this thread.
    
- No reads or writes of any variables/memory in the current thread can be reordered to happen before this acquire.
    
- The acquire acts as a one-way barrier when it comes to code reordering; reads and writes in the current thread can be moved down from _after_ the release to _before_ it. But, more importantly for synchronization, nothing can move down from _after_ the acquire to _before_ it.
    

With write/store/release of a particular atomic variable:

- All writes (atomic or non-atomic) in the current thread that happened before this release become visible to other threads that have read/loaded/acquired the same atomic variable.
    
- The value written to this atomic variable by this thread is also visible to other threads.
    
- No reads or writes of any variables/memory in the current thread can be reordered to happen after this release.
    
- The release acts as a one-way barrier when it comes to code reordering: reads and writes in the current thread can be moved up from _after_ the release to _before_ it. But, more importantly for synchronization, nothing can move down from _before_ the release to _after_ it.
    

Again, the upshot is synchronization of memory from one thread to another. The second thread can be sure that variables and memory are written in the order the programmer intended.

```
int x, y, z = 0;
atomic_int a = 0;

thread1() {
    x = 10;
    y = 20;
    a = 999;  // Release
    z = 30;
}

thread2()
{
    while (a != 999) { } // Acquire

    assert(x == 10);  // never asserts, x is always 10
    assert(y == 20);  // never asserts, y is always 20

    assert(z == 0);  // might assert!!
}
```

In the above example, `thread2` can be sure of the values in `x` and `y` after it acquires `a` because they were set before `thread1` released the atomic `a`.

But `thread2` can’t be sure of `z`’s value because it happened after the release. Maybe the assignment to `z` got moved before the assignment to `a`.

An important note: releasing one atomic variable has no effect on acquires of different atomic variables. Each variable is isolated from the others.

## 40.5 Sequential Consistency

You hanging in there? We’re through the meat of the simpler usage of atomics. And since we’re not even going to talk about the more complex uses here, you can relax a bit.

_Sequential consistency_ is what’s called a _memory ordering_. There are many memory orderings, but sequential consistency is the sanest[198](https://beej.us/guide/bgc/html/split/footnotes.html#fn198) C has to offer. It is also the default. You have to go out of your way to use other memory orderings.

All the stuff we’ve been talking about so far has happened within the realm of sequential consistency.

We’ve talked about how the compiler or CPU can rearrange memory reads and writes in a single thread as long as it follows the _as-if_ rule.

And we’ve seen how we can put the brakes on this behavior by synchronizing over atomic variables.

Let’s formalize just a little more.

If operations are _sequentially consistent_, it means at the end of the day, when all is said and done, all the threads can kick up their feet, open their beverage of choice, and all agree on the order in which memory changes occurred during the run. And that order is the one specified by the code.

One won’t say, “But didn’t _B_ happen before _A_?” if the rest of them say, “_A_ definitely happened before _B_”. They’re all friends, here.

In particular, within a thread, none of the acquires and releases can be reordered with respect to one another. This is in addition to the rules about what other memory accesses can be reordered around them.

This rule gives an additional level of sanity to the progression of atomic loads/acquires and stores/releases.

Every other memory order in C involves a relaxation of the reordering rules, either for acquires/releases or other memory accesses, atomic or otherwise. You’d do that if you _really_ knew what you were doing and needed the speed boost. _Here be armies of dragons…_

More on that later, but for now, let’s stick to the safe and practical.

## 40.6 Atomic Assignments and Operators

Certain operators on atomic variables are atomic. And others aren’t.

Let’s start with a counter-example:

```
atomic_int x = 0;

thread1() {
    x = x + 3;  // NOT atomic!
}
```

Since there’s a read of `x` on the right hand side of the assignment and a write effectively on the left, these are two operations. Another thread could sneak in the middle and make you unhappy.

But you _can_ use the shorthand `+=` to get an atomic operation:

```
atomic_int x = 0;

thread1() {
    x += 3;   // ATOMIC!
}
```

In that case, `x` will be atomically incremented by `3`—no other thread can jump in the middle.

In particular, the following operators are atomic read-modify-write operations with sequential consistency, so use them with gleeful abandon. (In the example, `a` is atomic.)

```
a++       a--       --a       ++a
a += b    a -= b    a *= b    a /= b    a %= b
a &= b    a |= b    a ^= b    a >>= b   a <<= b
```

## 40.7 Library Functions that Automatically Synchronize

So far we’ve talked about how you can synchronize with atomic variables, but it turns out there are a few library functions that do some limited behind-the-scenes synchronization, themselves.

```
call_once()      thrd_create()       thrd_join()
mtx_lock()       mtx_timedlock()     mtx_trylock()
malloc()         calloc()            realloc()
aligned_alloc()
```

[**`call_once()`**](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-call_once): synchronizes with all subsequent calls to `call_once()` for a particular flag. This way subsequent calls can rest assured that in another thread set the flag, they will see it.

[**`thrd_create()`**](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-thrd_create): synchronizes with the beginning of the new thread. The new thread can be sure it will see all shared memory writes from the parent thread from before the `thrd_create()` call.

[**`thrd_join()`**](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-thrd_join): when a thread dies, it synchronizes with this function. The thread that has called `thrd_join()` can be assured that it can see all the late thread’s shared writes.

[**`mtx_lock()`**](https://beej.us/guide/bgc/html/split/threads.html#man-mtx_lock): earlier calls to `mtx_unlock()` on the same mutex synchronize on this call. This is the case that most mirrors the acquire/release process we’ve already talked about. `mtx_unlock()` performs a release on the mutex variable, assuring any subsequent thread that makes an acquire with `mtx_lock()` can see all the shared memory changes in the critical section.

[**`mtx_timedlock()`**](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-mtx_timedlock) and [**`mtx_trylock()`**](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-mtx_trylock): similar to the situation with `mtx_lock()`, if this call succeeds, earlier calls to `mtx_unlock()` synchronize with this one.

**Dynamic Memory Functions**: if you allocate memory, it synchronizes with the previous deallocation of that same memory. And allocations and deallocations of that particular memory region happen in a single total order that all threads can agree upon. I _think_ the idea here is that the deallocation can wipe the region if it chooses, and we want to be sure that a subsequent allocation doesn’t see the non-wiped data. Someone let me know if there’s more to it.

## 40.8 Atomic Type Specifier, Qualifier

Let’s take it down a notch and see what types we have available, and how we can even make new atomic types.

First things first, let’s look at the built-in atomic types and what they are `typedef`’d to. (Spoiler: `_Atomic` is a type qualifier!)

Atomic type

Longhand equivalent

`atomic_bool`

`_Atomic _Bool`

`atomic_char`

`_Atomic char`

`atomic_schar`

`_Atomic signed char`

`atomic_uchar`

`_Atomic unsigned char`

`atomic_short`

`_Atomic short`

`atomic_ushort`

`_Atomic unsigned short`

`atomic_int`

`_Atomic int`

`atomic_uint`

`_Atomic unsigned int`

`atomic_long`

`_Atomic long`

`atomic_ulong`

`_Atomic unsigned long`

`atomic_llong`

`_Atomic long long`

`atomic_ullong`

`_Atomic unsigned long long`

`atomic_char16_t`

`_Atomic char16_t`

`atomic_char32_t`

`_Atomic char32_t`

`atomic_wchar_t`

`_Atomic wchar_t`

`atomic_int_least8_t`

`_Atomic int_least8_t`

`atomic_uint_least8_t`

`_Atomic uint_least8_t`

`atomic_int_least16_t`

`_Atomic int_least16_t`

`atomic_uint_least16_t`

`_Atomic uint_least16_t`

`atomic_int_least32_t`

`_Atomic int_least32_t`

`atomic_uint_least32_t`

`_Atomic uint_least32_t`

`atomic_int_least64_t`

`_Atomic int_least64_t`

`atomic_uint_least64_t`

`_Atomic uint_least64_t`

`atomic_int_fast8_t`

`_Atomic int_fast8_t`

`atomic_uint_fast8_t`

`_Atomic uint_fast8_t`

`atomic_int_fast16_t`

`_Atomic int_fast16_t`

`atomic_uint_fast16_t`

`_Atomic uint_fast16_t`

`atomic_int_fast32_t`

`_Atomic int_fast32_t`

`atomic_uint_fast32_t`

`_Atomic uint_fast32_t`

`atomic_int_fast64_t`

`_Atomic int_fast64_t`

`atomic_uint_fast64_t`

`_Atomic uint_fast64_t`

`atomic_intptr_t`

`_Atomic intptr_t`

`atomic_uintptr_t`

`_Atomic uintptr_t`

`atomic_size_t`

`_Atomic size_t`

`atomic_ptrdiff_t`

`_Atomic ptrdiff_t`

`atomic_intmax_t`

`_Atomic intmax_t`

`atomic_uintmax_t`

`_Atomic uintmax_t`

Use those at will! They’re consistent with the atomic aliases found in C++, if that helps.

But what if you want more?

You can do it either with a type qualifier or type specifier.

First, specifier! It’s the keyword `_Atomic` with a type in parens after[199](https://beej.us/guide/bgc/html/split/footnotes.html#fn199)—suitable for use with `typedef`:

```
typedef _Atomic(double) atomic_double;

atomic_double f;
```

Restrictions on the specifier: the type you’re making atomic can’t be of type array or function, nor can it be atomic or otherwise qualified.

Next, qualifier! It’s the keyword `_Atomic` _without_ a type in parens.

So these do similar things[200](https://beej.us/guide/bgc/html/split/footnotes.html#fn200):

```
_Atomic(int) i;   // type specifier
_Atomic int  j;   // type qualifier
```

The thing is, you can include other type qualifiers with the latter:

```
_Atomic volatile int k;   // qualified atomic variable
```

Restrictions on the qualifier: the type you’re making atomic can’t be of type array or function.

## 40.9 Lock-Free Atomic Variables

Hardware architectures are limited in the amount of data they can atomically read and write. It depends on how it’s wired together. And it varies.

If you use an atomic type, you can be assured that accesses to that type will be atomic… but there’s a catch: if the hardware can’t do it, it’s done with a lock, instead.

So the atomic access becomes lock-access-unlock, which is rather slower and has some implications for signal handlers.

[Atomic flags](https://beej.us/guide/bgc/html/split/chapter-atomics.html#atomic-flags), below, is the only atomic type that is guaranteed to be lock-free in all conforming implementations. In typical desktop/laptop computer world, other larger types are likely lock-free.

Luckily, we have a couple ways to determine if a particular type is a lock-free atomic or not.

First of all, some macros—you can use these at compile time with `#if`. They apply to both signed and unsigned types.

Atomic Type

Lock Free Macro

`atomic_bool`

`ATOMIC_BOOL_LOCK_FREE`

`atomic_char`

`ATOMIC_CHAR_LOCK_FREE`

`atomic_char16_t`

`ATOMIC_CHAR16_T_LOCK_FREE`

`atomic_char32_t`

`ATOMIC_CHAR32_T_LOCK_FREE`

`atomic_wchar_t`

`ATOMIC_WCHAR_T_LOCK_FREE`

`atomic_short`

`ATOMIC_SHORT_LOCK_FREE`

`atomic_int`

`ATOMIC_INT_LOCK_FREE`

`atomic_long`

`ATOMIC_LONG_LOCK_FREE`

`atomic_llong`

`ATOMIC_LLONG_LOCK_FREE`

`atomic_intptr_t`

`ATOMIC_POINTER_LOCK_FREE`

These macros can interestingly have _three_ different values:

Value

Meaning

`0`

Never lock-free.

`1`

_Sometimes_ lock-free.

`2`

Always lock-free.

Wait—how can something be _sometimes_ lock-free? This just means the answer isn’t known at compile-time, but could later be known at runtime. Maybe the answer varies depending on whether or not you’re running this code on Genuine Intel or AMD, or something like that[201](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn201).

But you can always test at runtime with the `atomic_is_lock_free()` function. This function returns true or false if the particular type is atomic right now.

So why do we care?

Lock-free is faster, so maybe there’s a speed concern that you’d code around another way. Or maybe you need to use an atomic variable in a signal handler.

### 40.9.1 Signal Handlers and Lock-Free Atomics

If you read or write a shared variable (static storage duration or `_Thread_Local`) in a signal handler, it’s undefined behavior \[gasp!\]… Unless you do one of the following:

1. Write to a variable of type `volatile sig_atomic_t`.
    
2. Read or write a lock-free atomic variable.
    

As far as I can tell, lock-free atomic variables are one of the few ways you get portably get information out of a signal handler.

The spec is a bit vague, in my read, about the memory order when it comes to acquiring or releasing atomic variables in the signal handler. C++ says, and it makes sense, that such accesses are unsequenced with respect to the rest of the program[202](https://beej.us/guide/bgc/html/split/footnotes.html#fn202). The signal can be raised, after all, at any time. So I’m assuming C’s behavior is similar.

## 40.10 Atomic Flags

There’s only one type the standard guarantees will be a lock-free atomic: `atomic_flag`. This is an opaque type for [test-and-set](https://en.wikipedia.org/wiki/Test-and-set)[203](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn203) operations.

It can be either _set_ or _clear_. You can initialize it to clear with:

```
atomic_flag f = ATOMIC_FLAG_INIT;
```

You can set the flag atomically with `atomic_flag_test_and_set()`, which will set the flag and return its previous status as a `_Bool` (true for set).

You can clear the flag atomically with `atomic_flag_clear()`.

Here’s an example where we init the flag to clear, set it twice, then clear it again.

```
#include <stdio.h>
#include <stdbool.h>
#include <stdatomic.h>

atomic_flag f = ATOMIC_FLAG_INIT;

int main(void)
{
    bool r = atomic_flag_test_and_set(&f);
    printf("Value was: %d\n", r);           // 0

    r = atomic_flag_test_and_set(&f);
    printf("Value was: %d\n", r);           // 1

    atomic_flag_clear(&f);
    r = atomic_flag_test_and_set(&f);
    printf("Value was: %d\n", r);           // 0
}
```

## 40.11 Atomic `struct`s and `union`s

Using the `_Atomic` qualifier or specifier, you can make atomic `struct`s or `union`s! Pretty astounding.

If there’s not a lot of data in there (i.e. a handful of bytes), the resulting atomic type might be lock-free. Test it with `atomic_is_lock_free()`.

```
#include <stdio.h>
#include <stdatomic.h>

int main(void)
{
    struct point {
        float x, y;
    };

    _Atomic(struct point) p;

    printf("Is lock free: %d\n", atomic_is_lock_free(&p));
}
```

Here’s the catch: you can’t access fields of an atomic `struct` or `union`… so what’s the point? Well, you can atomically _copy_ the entire `struct` into a non-atomic variable and then used it. You can atomically copy the other way, too.

```
#include <stdio.h>
#include <stdatomic.h>

int main(void)
{
    struct point {
        float x, y;
    };

    _Atomic(struct point) p;
    struct point t;

    p = (struct point){1, 2};  // Atomic copy

    //printf("%f\n", p.x);  // Error

    t = p;   // Atomic copy

    printf("%f\n", t.x);  // OK!
}
```

You can also declare a `struct` where individual fields are atomic. It is implementation defined if atomic types are allowed on bitfields.

## 40.12 Atomic Pointers

Just a note here about placement of `_Atomic` when it comes to pointers.

First, pointers to atomics (i.e. the pointer value is not atomic, but the thing it points to is):

```
_Atomic int x;
_Atomic int *p;  // p is a pointer to an atomic int

p = &x;  // OK!
```

Second, atomic pointers to non-atomic values (i.e. the pointer value itself is atomic, but the thing it points to is not):

```
int x;
int * _Atomic p;  // p is an atomic pointer to an int

p = &x;  // OK!
```

Lastly, atomic pointers to atomic values (i.e. the pointer and the thing it points to are both atomic):

```
_Atomic int x;
_Atomic int * _Atomic p;  // p is an atomic pointer to an atomic int

p = &x;  // OK!
```

## 40.13 Memory Order

We’ve already talked about sequential consistency, which is the sensible one of the bunch. But there are a number of other ones:

`memory_order`

Description

`memory_order_seq_cst`

Sequential Consistency

`memory_order_acq_rel`

Acquire/Release

`memory_order_release`

Release

`memory_order_acquire`

Acquire

`memory_order_consume`

Consume

`memory_order_relaxed`

Relaxed

You can specify other ones with certain library functions. For example, you can add a value to an atomic variable like this:

```
atomic_int x = 0;

x += 5;  // Sequential consistency, the default
```

or you can do the same with this library function:

```
atomic_int x = 0;

atomic_fetch_add(&x, 5);  // Sequential consistency, the default
```

or you can do the same thing with an explicit memory ordering:

```
atomic_int x = 0;

atomic_fetch_add_explicit(&x, 5, memory_order_seq_cst);
```

But what if we didn’t want sequential consistency? And you wanted acquire/release instead for whatever reason? Just name it:

```
atomic_int x = 0;

atomic_fetch_add_explicit(&x, 5, memory_order_acq_rel);
```

We’ll do a breakdown of the different memory orders, below. Don’t mess with anything other than sequential consistency unless you know what you’re doing. It’s really easy to make mistakes that will cause rare, hard-to-repro failures.

### 40.13.1 Sequential Consistency

- Load operations acquire (see below).
- Store operations release (see below).
- Read-modify-write operations acquire then release.

Also, in order to maintain the total order of acquires and releases, no acquires or releases will be reordered with respect to each other. (The acquire/release rules do not forbid reordering a release followed by an acquire. But the sequentially consistent rules do.)

### 40.13.2 Acquire

This is what happens on a load/read operation on an atomic variable.

- If another thread released this atomic variable, all the writes that thread did are now visible in this thread.
    
- Memory accesses in this thread that happen after this load can’t be reordered before it.
    

### 40.13.3 Release

This is what happens on a store/write of an atomic variable.

- If another thread later acquires this atomic variable, all memory writes in this thread before its atomic write become visible to that other thread.
    
- Memory accesses in this thread that happen before the release can’t be reordered after it.
    

### 40.13.4 Consume

This is an odd one, similar to a less-strict version of acquire. It affects memory accesses that are _data dependent_ on the atomic variable.

Being “data dependent” vaguely means that the atomic variable is used in a calculation.

That is, if a thread consumes an atomic variable then all the operations in that thread that go on to use that atomic variable will be able to see the memory writes in the releasing thread.

Compare to acquire where memory writes in the releasing thread will be visible to _all_ operations in the current thread, not just the data-dependent ones.

Also like acquire, there is a restriction on which operations can be reordered _before_ the consume. With acquire, you couldn’t reorder anything before it. With consume, you can’t reorder anything that depends on the loaded atomic value before it.

### 40.13.5 Acquire/Release

This only applies to read-modify-write operations. It’s an acquire and release bundled into one.

- An acquire happens for the read.
- A release happens for the write.

### 40.13.6 Relaxed

No rules; it’s anarchy! Everyone can reorder everything everywhere! Dogs and cats living together—mass hysteria!

Actually, there is a rule. Atomic reads and writes are still all-or-nothing. But the operations can be reordered whimsically and there is zero synchronization between threads.

There are a few use cases for this memory order, which you can find with a tiny bit of searching, e.g. simple counters.

And you can use a fence to force synchronization after a bunch of relaxed writes.

## 40.14 Fences

You know how the releases and acquires of atomic variables occur as you read and write them?

Well, it’s possible to do a release or acquire _without_ an atomic variable, as well.

This is called a _fence_. So if you want all the writes in a thread to be visible elsewhere, you can put up a release fence in one thread and an acquire fence in another, just like with how atomic variables work.

Since a consume operation doesn’t really make sense on a fence[204](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn204), `memory_order_consume` is treated as an acquire.

You can put up a fence with any specified order:

```
atomic_thread_fence(memory_order_release);
```

There’s also a light version of a fence for use with signal handlers, called `atomic_signal_fence()`.

It works just the same way as `atomic_thread_fence()`, except:

- It only deals with visibility of values within the same thread; there is no synchronization with other threads.
    
- No hardware fence instructions are emitted.
    

If you want to be sure the side effects of non-atomic operations (and relaxed atomic operations) are visible in the signal handler, you can use this fence.

The idea is that the signal handler is executing in _this_ thread, not another, so this is a lighter-weight way of making sure changes outside the signal handler are visible within it (i.e. they haven’t been reordered).

## 40.15 References

If you want to learn more about this stuff, here are some of the things that helped me plow through it:

- Herb Sutter’s _`atomic<>` Weapons_ talk:
    
    - [Part 1](https://channel9.msdn.com/Shows/Going+Deep/Cpp-and-Beyond-2012-Herb-Sutter-atomic-Weapons-1-of-2)[205](https://beej.us/guide/bgc/html/split/footnotes.html#fn205)
    - [part 2](https://channel9.msdn.com/Shows/Going+Deep/Cpp-and-Beyond-2012-Herb-Sutter-atomic-Weapons-2-of-2)[206](https://beej.us/guide/bgc/html/split/footnotes.html#fn206)
- [Jeff Preshing’s materials](https://preshing.com/archives/)[207](https://beej.us/guide/bgc/html/split/footnotes.html#fn207), in particular:
    
    - [An Introduction to Lock-Free Programming](https://preshing.com/20120612/an-introduction-to-lock-free-programming/)[208](https://beej.us/guide/bgc/html/split/footnotes.html#fn208)
    - [Acquire and Release Semantics](https://preshing.com/20120913/acquire-and-release-semantics/)[209](https://beej.us/guide/bgc/html/split/footnotes.html#fn209)
    - [The _Happens-Before_ Relation](https://preshing.com/20130702/the-happens-before-relation/)[210](https://beej.us/guide/bgc/html/split/footnotes.html#fn210)
    - [The _Synchronizes-With_ Relation](https://preshing.com/20130823/the-synchronizes-with-relation/)[211](https://beej.us/guide/bgc/html/split/footnotes.html#fn211)
    - [The Purpose of `memory_order_consume` in C++11](https://preshing.com/20140709/the-purpose-of-memory_order_consume-in-cpp11/)[212](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn212)
    - [You Can Do Any Kind of Atomic Read-Modify-Write Operation](https://preshing.com/20150402/you-can-do-any-kind-of-atomic-read-modify-write-operation/)[213](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn213)
- CPPReference:
    
    - [Memory Order](https://en.cppreference.com/w/c/atomic/memory_order)[214](https://beej.us/guide/bgc/html/split/footnotes.html#fn214)
    - [Atomic Types](https://en.cppreference.com/w/c/language/atomic)[215](https://beej.us/guide/bgc/html/split/footnotes.html#fn215)
- Bruce Dawson’s [Lockless Programming Considerations](https://docs.microsoft.com/en-us/windows/win32/dxtecharts/lockless-programming)[216](https://beej.us/guide/bgc/html/split/footnotes.html#fn216)
    
- The helpful and knowledgeable folks on [r/C\_Programming](https://www.reddit.com/r/C_Programming/)[217](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn217)
    

# 41 Function Specifiers, Alignment Specifiers/Operators

These don’t see a heck of a lot of use in my experience, but we’ll cover them here for the sake of completeness.

## 41.1 Function Specifiers

When you declare a function, you can give the compiler a couple tips about how the functions could or will be used. This enables or encourages the compiler to make certain optimizations.

### 41.1.1 `inline` for Speed—Maybe

You can declare a function to be inline like this:

```
static inline int add(int x, int y) {
    return x + y;
}
```

This is meant to encourage the compiler to make this function call as fast as possible. And, historically, one way to do this was _inlining_, which means that the body of the function would be embedded in its entirety where the call was made. This would avoid all the overhead of setting up the function call and tearing it down at the expense of larger code size as the function was copied all over the place instead of being reused.

That would seem to be the end of the story, but it’s not. `inline` comes with a whole pile of rules that make for _interesting times_. I’m not sure I even understand them all, and behavior seems to vary from compiler to compiler.

The short answer is define the `inline` function as `static` in the file that you need it. And then use it in that one file. And you never have to worry about the rest of it.

But if you’re wondering, here are more fun times.

Let’s try leaving the `static` off.

```
#include <stdio.h>

inline int add(int x, int y)
{
    return x + y;
}

int main(void)
{
    printf("%d\n", add(1, 2));
}
```

`gcc` gives a linker error on `add()`… unless you compile with optimizations on (probably)!

See, a compiler can choose to inline or not, but if it chooses not to, you’re left with no function at all. `gcc` doesn’t inline unless you’re doing an optimized build.

One way around this is to define a non-`inline` external linkage version of the function elsewhere, and that one will be used when the `inline` one isn’t. But you as the programmer can’t determine which, portably. If both are available, it’s unspecified which one the compiler chooses. With `gcc` the inline function will be used if you’re compiling with optimizations, and the non-inline one will be used otherwise. Even if the bodies of these functions are completely different. Zany!

Another way is to declare the function as `extern inline`. This will attempt to inline in this file, but will also create a version with external linkage. And so `gcc` will use one or the other depending on optimizations, but at least they’re the same function.

Unless, of course, you have another source file with an `inline` function of the same name; it will use its `inline` function or the one with external linkage depending on optimizations.

But let’s say you’re doing a build where the compiler _is_ inlining the function. In that case, you can just use a plain `inline` in the definition. However, there are now additional restrictions.

You can’t refer to any `static` globals:

```
static int b = 13;

inline int add(int x, int y)
{
    return x + y + b;  // BAD -- can't refer to b
}
```

And you can’t define any non-`const` `static` local variables:

```
inline int add(int x, int y)
{
    static int b = 13;  // BAD -- can't define static

    return x + y + b;
}
```

But making it `const` is OK:

```
inline int add(int x, int y)
{
    static const int b = 13;  // OK -- static const

    return x + y + b;
}
```

Now, you know the functions are `extern` by default, so we should be able to call `add()` from another file. You’d like to think that, wouldn’t you!

But you can’t! If it’s just a plain `inline`, it’s similar to `static`: it’s only visible in that file.

Okay, so what if you throw an `extern` on there? Now we’re coming full circle to when we discussed having `inline` mixed with functions with external linkage.

If both are visible, the compiler can choose which to use.

Let’s do a demo of this behavior. We’ll have two files, `foo.c` and `bar.c`. They’ll both call `func()` which is `inline` in `foo.c` and external linkage in `bar.c`.

Here’s `foo.c` with the `inline`.

```
// foo.c

#include <stdio.h>

inline char *func(void)
{
    return "foo's function";
}

int main(void)
{
    printf("foo.c: %s\n", func());

    void bar(void);
    bar();
}
```

Recall that unless we’re doing an optimized build with `gcc`. `func()` will vanish and we’ll get a linker error. Unless, or course, we have a version with external linkage defined elsewhere.

And we do. In `bar.c`.

```
// bar.c

#include <stdio.h>

char *func(void)
{
    return "bar's function";
}

void bar(void)
{
    printf("bar.c: %s\n", func());
}
```

So the question is, what is the output?

Seems like when we call `func()` from `foo.c`, it should print “`foo's function`”. And from `bar.c`, that `func()` should print “`bar's function`”.

And if I compile with `gcc` with optimizations[218](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn218) it will use inline functions, and we’ll get the expected:

```
foo.c: foo's function
bar.c: bar's function
```

Great!

But if we compile in `gcc` without optimizations, it ignores the inline function and uses the external linkage `func()` from `bar.c`! And we get this:

```
foo.c: bar's function
bar.c: bar's function
```

In short, the rules are surprisingly complex. I give myself a good 30% chance of having described them correctly.

### 41.1.2 `noreturn` and `_Noreturn`

This indicates to the compiler that a particular function will not ever return to its caller, i.e. the program will exit by some mechanism before the function returns.

It allows the compiler to perhaps perform some optimizations around the function call.

It also allows you to indicate to other devs that some program logic depends on a function _not_ returning.

You’ll likely never need to use this, but you’ll see it on some library calls like [`exit()`](https://beej.us/guide/bgc/html/split/stdlib.html#man-exit) and [`abort()`](https://beej.us/guide/bgc/html/split/chapter-atomics.html#man-abort).

The built-in keyword is `_Noreturn`, but if it doesn’t break your existing code, everyone would recommend including `<stdnoreturn.h>` and using the easier-to-read `noreturn` instead.

It’s undefined behavior if a function specified as `noreturn` actually does return. It’s computationally dishonest, see.

Here’s an example of using `noreturn` correctly:

```
#include <stdio.h>
#include <stdlib.h>
#include <stdnoreturn.h>

noreturn void foo(void) // This function should never return!
{
    printf("Happy days\n");

    exit(1);            // And it doesn't return--it exits here!
}

int main(void)
{
    foo();
}
```

If the compiler detects that a `noreturn` function could return, it might warn you, helpfully.

Replacing the `foo()` function with this:

```
noreturn void foo(void)
{
    printf("Breakin' the law\n");
}
```

gets me a warning:

```
foo.c:7:1: warning: function declared 'noreturn' should not return
```

## 41.2 Alignment Specifiers and Operators

[_Alignment_](https://en.wikipedia.org/wiki/Data_structure_alignment)[219](https://beej.us/guide/bgc/html/split/chapter-atomics.html#fn219) is all about multiples of addresses on which objects can be stored. Can you store this at any address? Or must it be a starting address that’s divisible by 2? Or 8? Or 16?

If you’re coding up something low-level like a memory allocator that interfaces with your OS, you might need to consider this. Most devs go their careers without using this functionality in C.

### 41.2.1 `alignas` and `_Alignas`

This isn’t a function. Rather, it’s an _alignment specifier_ that you can use with a variable declaration.

The built-in specifier is `_Alignas`, but the header `<stdalign.h>` defines it as `alignas` for something better looking.

If you need your `char` to be aligned like an `int`, you can force it like this when you declare it:

```
char alignas(int) c;
```

You can also pass a constant value or expression in for the alignment. This has to be something supported by the system, but the spec stops short of dictating what values you can put in there. Small powers of 2 (1, 2, 4, 8, and 16) are generally safe bets.

```
char alignas(8) c;   // align on 8-byte boundaries
```

If you want to align at the maximum used alignment by your system, include `<stddef.h>` and use the type `max_align_t`, like so:

```
char alignas(max_align_t) c;
```

You could potentially _over-align_ by specifying an alignment more than that of `max_align_t`, but whether or not such things are allowed is system dependent.

### 41.2.2 `alignof` and `_Alignof`

This operator will return the address multiple a particular type uses for alignment on this system. For example, maybe `char`s are aligned every 1 address, and `int`s are aligned every 4 addresses.

The built-in operator is `_Alignof`, but the header `<stdalign.h>` defines it as `alignof` if you want to look cooler.

Here’s a program that will print out the alignments of a variety of different types. Again, these will vary from system to system. Note that the type `max_align_t` will give you the maximum alignment used by the system.

```
#include <stdalign.h>
#include <stdio.h>     // for printf()
#include <stddef.h>    // for max_align_t

struct t {
    int a;
    char b;
    float c;
};

int main(void)
{
    printf("char       : %zu\n", alignof(char));
    printf("short      : %zu\n", alignof(short));
    printf("int        : %zu\n", alignof(int));
    printf("long       : %zu\n", alignof(long));
    printf("long long  : %zu\n", alignof(long long));
    printf("double     : %zu\n", alignof(double));
    printf("long double: %zu\n", alignof(long double));
    printf("struct t   : %zu\n", alignof(struct t));
    printf("max_align_t: %zu\n", alignof(max_align_t));
}
```

Output on my system:

```
char       : 1
short      : 2
int        : 4
long       : 8
long long  : 8
double     : 8
long double: 16
struct t   : 16
max_align_t: 16
```

And there you have it. Alignment!