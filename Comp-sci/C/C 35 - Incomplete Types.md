# 35 Incomplete Types

It might surprise you to learn that this builds without error:

```
extern int a[];

int main(void)
{
    struct foo *x;
    union bar *y;
    enum baz *z;
}
```

We never gave a size for `a`. And we have pointers to `struct`s `foo`, `bar`, and `baz` that never seem to be declared anywhere.

And the only warnings I get are that `x`, `y`, and `z` are unused.

These are examples of _incomplete types_.

An incomplete type is a type the size (i.e. the size you’d get back from `sizeof`) for which is not known. Another way to think of it is a type that you haven’t finished declaring.

You can have a pointer to an incomplete type, but you can’t dereference it or use pointer arithmetic on it. And you can’t `sizeof` it.

So what can you do with it?

## 35.1 Use Case: Self-Referential Structures

I only know of one real use case: forward references to `struct`s or `union`s with self-referential or co-dependent structures. (I’m going to use `struct` for the rest of these examples, but they all apply equally to `union`s, as well.)

Let’s do the classic example first.

But before I do, know this! As you declare a `struct`, the `struct` is incomplete until the closing brace is reached!

```
struct antelope {              // struct antelope is incomplete here
    int leg_count;             // Still incomplete
    float stomach_fullness;    // Still incomplete
    float top_speed;           // Still incomplete
    char *nickname;            // Still incomplete
};                             // NOW it's complete.
```

So what? Seems sane enough.

But what if we’re doing a linked list? Each linked list node needs to have a reference to another node. But how can we create a reference to another node if we haven’t finished even declaring the node yet?

C’s allowance for incomplete types makes it possible. We can’t declare a node, but we _can_ declare a pointer to one, even if it’s incomplete!

```
struct node {
    int val;
    struct node *next;  // struct node is incomplete, but that's OK!
};
```

Even though the `struct node` is incomplete on line 3, we can still declare a pointer to one[171](https://beej.us/guide/bgc/html/split/footnotes.html#fn171).

We can do the same thing if we have two different `struct`s that refer to each other:

```
struct a {
    struct b *x;  // Refers to a `struct b`
};

struct b {
    struct a *x;  // Refers to a `struct a`
};
```

We’d never be able to make that pair of structures without the relaxed rules for incomplete types.

## 35.2 Incomplete Type Error Messages

Are you getting errors like these?

```
invalid application of ‘sizeof’ to incomplete type

invalid use of undefined type

dereferencing pointer to incomplete type
```

Most likely culprit: you probably forgot to `#include` the header file that declares the type.

## 35.3 Other Incomplete Types

Declaring a `struct` or `union` with no body makes an incomplete type, e.g. `struct foo;`.

`enums` are incomplete until the closing brace.

`void` is an incomplete type.

Arrays declared `extern` with no size are incomplete, e.g.:

```
extern int a[];
```

If it’s a non-`extern` array with no size followed by an initializer, it’s incomplete until the closing brace of the initializer.

## 35.4 Use Case: Arrays in Header Files

It can be useful to declare incomplete array types in header files. In those cases, the actual storage (where the complete array is declared) should be in a single `.c` file. If you put it in the `.h` file, it will be duplicated every time the header file is included.

So what you can do is make a header file with an incomplete type that refers to the array, like so:

```
// File: bar.h

#ifndef BAR_H
#define BAR_H

extern int my_array[];  // Incomplete type

#endif
```

And the in the `.c` file, actually define the array:

```
// File: bar.c

int my_array[1024];     // Complete type!
```

Then you can include the header from as many places as you’d like, and every one of those places will refer to the same underlying `my_array`.

```
// File: foo.c

#include <stdio.h>
#include "bar.h"    // includes the incomplete type for my_array

int main(void)
{
    my_array[0] = 10;

    printf("%d\n", my_array[0]);
}
```

When compiling multiple files, remember to specify all the `.c` files to the compiler, but not the `.h` files, e.g.:

```
gcc -o foo foo.c bar.c
```

## 35.5 Completing Incomplete Types

If you have an incomplete type, you can complete it by defining the complete `struct`, `union`, `enum`, or array in the same scope.

```
struct foo;        // incomplete type

struct foo *p;     // pointer, no problem

// struct foo f;   // Error: incomplete type!

struct foo {
    int x, y, z;
};                 // Now the struct foo is complete!

struct foo f;      // Success!
```

Note that though `void` is an incomplete type, there’s no way to complete it. Not that anyone ever thinks of doing that weird thing. But it does explain why you can do this:

```
void *p;             // OK: pointer to incomplete type
```

and not either of these:

```
void v;              // Error: declare variable of incomplete type

printf("%d\n", *p);  // Error: dereference incomplete type
```

The more you know…