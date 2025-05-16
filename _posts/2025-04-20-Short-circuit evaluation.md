---
title: Short-circuit evaluation
date: 2025-04-20
categories: [Computer Science]
tags: [cs]     # TAG names should always be lowercase
image:
  path: assets/posts-covers/Short-Circuit Evaluation-3.png
---

**Short-circuit evaluation** is a programming language feature where the second part of the logical expression is **not evaluated** if the result can already be determined from the first part.

---

## Logical Operators

- **Logical AND (`&&` or `and`)**  
  Evaluates to `true` if **both** operands are true.  
    - If the first operand is false, the overall result must be false, so the second operand is `not` evaluated.

- **Logical OR (`||` or `or`)**  
  Evaluates to `true` if **either** operand is true.  
    - If the first operand is true, the overall result is already true, so the second operand is `not` evaluated.

---

## Why It Matters

1. **Performance**  
   Avoids unnecessary computation (especially if the second operand is expensive to compute).

2. **Safety**  
   Prevents runtime errors by guarding expressions—for example, checking for `null` before accessing a property.

3. **Control Flow**  
   Can be used to execute conditional side-effects in many languages.

---

## Examples

```python
def func():
    # ...
    return False

x = False and func()
# func() is not called; x == False

y = True or func()
# func() is not called; y == True
```

```c
#include <stdio.h>
#include <stdbool.h>

bool func() 
{
    // ...
    return false;
}

int main() 
{
    bool a = false && func();
    // a == false, and 'func' is not called

    bool b = true || func();
    // b == true, and 'func' is not called

    return 0;
}
```

---

## Use Cases

```c
int denom;
if (denom != 0 && num / denom == a)
{
    // ...
    // Prevents division by zero:
    // If 'denom' is 0, the first condition fails, so 'num / denom' is never evaluated.
    // This avoids a potential runtime error.
}
```

---

## Possible Problems

```c
if (expressionA && myfunc(b)) 
{
    do_something();
}
```

If `myfunc(b)` is supposed to perform some required operation, such as allocating system resources, and `expressionA` evaluates as false, then `myfunc(b)` will not execute, which could cause problems.

```c
if (expressionA || myfunc(b)) 
{
    do_something();
}
```

If `myfunc(b)` is supposed to perform some required operation, and `expressionA` evaluates as true, then `myfunc(b)` will not execute, which could cause problems.

---

## Possible Fix

```c
bool result = myfunc(b);  // Ensure it's called

if (expressionA && result)
{
    do_something();
}
```

This ensures that `myfunc(b)` is always called while still participating in the conditional check.  
