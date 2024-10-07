# 42 `<assert.h>` Runtime and Compile-time Diagnostics

Macro

Description

`assert()`

Runtime assertion

`static_assert()`

Compile-time assertion

This functionality has to do with things that Should Never Happen™. If you have something that should never be true and you want your program to bomb out because it happened, this is the header file for you.

There are two types of assertions: compile-time assertions (called “static assertions”) and runtime assertions. If the assertion _fails_ (i.e. the thing that you need to be true is not true) then the program will bomb out either at compile-time or runtime.

## 42.1 Macros

If you define the macro `NDEBUG` **before** you include `<assert.h>`, then the `assert()` macro will have no effect. You can define `NDEBUG` to be anything, but `1` seems like a good value.

Since `assert()` causes your program to bomb out at runtime, you might not desire this behavior when you go into production. Defining `NDEBUG` causes `assert()` to be ignored.

`NDEBUG` has no effect on `static_assert()`.

* * *

## 42.2 `assert()`

Bomb out at runtime if a condition fails

### Synopsis

```
#include <assert.h>

void assert(scalar expression);
```

### Description

You pass in an expression to this macro. If it evaluates to false, the program will crash with an assertion failure (by calling the `abort()` function).

Basically, you’re saying, “Hey, I’m assuming this condition is true, and if it’s not, I don’t want to continue running.”

This is used while debugging to make sure no unexpected conditions arise. And if you find during development that the condition does arise, maybe you should modify the code to handle it before going to production.

If you’ve defined the macro `NDEBUG` to any value before `<assert.h>` was included, the `assert()` macro is ignored. This is a good idea before production.

Unlike `static_assert()`, this macro doesn’t allow you to print an arbitrary message. If you want to do this, check out [the example in the Preprocessor chapter](https://beej.us/guide/bgc/html/split/assert.html#my-assert).

### Return Value

This macro doesn’t return (since it calls `abort()` which never returns).

If `NDEBUG` is set, the macro evaluates to `((void)0)`, which does nothing.

### Example

Here’s a function that divides the size of our goat herd. But we’re assuming we’ll never get a `0` passed to us.

So we assert that `amount != 0`… and if it is, the program aborts/

```
//#define NDEBUG 1   // uncomment this to disable the assert

#include <stdio.h>
#include <assert.h>

int goat_count = 10;

void divide_goat_herd_by(int amount)
{
    assert(amount != 0);

    goat_count /= amount;
}  

int main(void)
{
    divide_goat_herd_by(2);  // OK

    divide_goat_herd_by(0);  // Causes the assert to fire
}
```

When I run this and pass `0` to the function, I get the following on my system (the exact output may vary):

```
assert: assert.c:10: divide_goat_herd_by: Assertion `amount != 0' failed.
```

### See Also

[`static_assert()`](https://beej.us/guide/bgc/html/split/assert.html#man-static_assert), [`abort()`](https://beej.us/guide/bgc/html/split/assert.html#man-abort)

* * *

## 42.3 `static_assert()`

Bomb out at compile-time if a condition fails

### Synopsis

```
#include <assert.h>

static_assert(constant-expression, string-literal);
```

### Description

This macro prevents your program from even compiling if a condition isn’t true.

And it prints the string literal you give it.

Basically if `constant-expression` is false, then compilation will cease and the `string-literal` will be printed.

The constant expression must be truly constant–just values, no variables. And the same is true for the string literal: no variables, just a literal string in double quotes. (It has to be this way since the program’s not running at this point.)

### Return Value

Not applicable, as this is a compile-time feature.

### Example

Here’s a partial example with an algorithm that presumably has poor performance or memory issues if the size of the local array is too large. We prevent that eventuality at compile-time by catching it with the `static_assert()`.

```
#include <stdio.h>
#include <assert.h>

#define ARRAY_SIZE 16

int main(void)
{
    static_assert(ARRAY_SIZE > 32, "ARRAY_SIZE too small");

    int a[ARRAY_SIZE];

    a[32] = 10;

    printf("%d\n", a[32]);
}
```

On my system, when I try to compile it, this prints (your output may vary):

```
In file included from static_assert.c:2:
static_assert.c: In function ‘main’:
static_assert.c:8:5: error: static assertion failed: "ARRAY_SIZE too small"
    8 |     static_assert(ARRAY_SIZE > 32, "ARRAY_SIZE too small");
      |     ^~~~~~~~~~~~~
```

### See Also

[`assert()`](https://beej.us/guide/bgc/html/split/assert.html#man-assert)