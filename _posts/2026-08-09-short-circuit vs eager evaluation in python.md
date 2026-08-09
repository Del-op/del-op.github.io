---
title: Short-Circuit vs Eager Evaluation in Python
date: 2026-08-09
categories: [Computer Science, Python]
tags: [eager evaluation]
image:
  path: assets/posts-covers/first_or_second.png
---

This post builds on the previous post [Short-Circuit Evaluation](https://del-op.github.io/posts/short-circuit-evaluation){:target="_blank"}. I recommend reading it before proceeding with this one.

Here, the focus is specifically on how short-circuit and eager evaluation work in **Python**.

---


Python has two pairs of operators that can look similar:

- Logical: `and`, `or`
- Bitwise: `&`, `|`

The important difference in evaluation is:

`and` and `or` **short-circuit**: Python may skip the right-hand expression when the result can already be determined from the left-hand operand.

`&` and `|`, like ordinary binary operators in Python, evaluate **both operand expressions before the operator is applied**.

---

## Short-Circuit Evaluation

```python
def check():
    print("called")
    return True

False and check()
True or check()
```

`check()` is never called.

This is useful for safe conditions:

```python
obj = None

if obj is not None and obj.value > 10:
    print("Success")
```

If `obj` is `None`, Python skips the second expression and avoids an error.

---

`and` and `or` are special language-level expressions whose semantics determine whether the right-hand expression is evaluated at all.

```python
x and y
```

behaves approximately like:

```text
evaluate x

if x is falsy:
    return x

otherwise:
    evaluate and return y
```

Likewise:

```python
x or y
```

behaves approximately like:

```text
evaluate x

if x is truthy:
    return x

otherwise:
    evaluate and return y
```

This also means that `and` and `or` do not necessarily return Boolean values.

For example:

```python
"hello" and 42
# 42

"" or "fallback"
# "fallback"
```

They return one of their operands.

---

## Bitwise Operators

`&` and `|` are primarily used for operations on bits.

```python
12 & 25  # 8
```

For example:

```text
  01100   # 12
& 11001   # 25
-------
  01000   # 8
```

They also work with Booleans:

```python
True & False  # False
True | False  # True
```

Python's `bool` type is a subclass of `int`, with `True` corresponding numerically to `1` and `False` to `0`.

However, unlike `and` and `or`, both operands are still evaluated:

```python
def first():
    print("first")
    return True

def second():
    print("second")
    return True

first() or second()
# first

first() | second()
# first
# second
```

A useful conceptual model is:

```text
first() | second()

1. evaluate first()
2. evaluate second()
3. apply |
```

This is an example of **eager operand evaluation**: both operand expressions are evaluated before the operator is applied.

Python's `&` and `|` are fundamentally bitwise operator forms, but **being bitwise is not what makes them eager**; their eager operand evaluation follows from Python's general semantics for ordinary binary expressions.

Some languages expose eager and short-circuit logical operations separately. Ada is one example.[^1]

---

## When `&` and `|` Are Useful

### Bit Flags

```python
READ  = 0b100
WRITE = 0b010

permissions = READ | WRITE

if permissions & WRITE:
    print("Write enabled")
```

### Element-Wise Operations in NumPy

Another important use appears in libraries such as NumPy.

Suppose `a` is a NumPy array:

```python
(a > 0) & (a < 10)
```

> The parentheses are important because comparison and bitwise operators have different precedence rules.

Each comparison first produces an array of Boolean values.

Conceptually:

```text
a > 0
    |
    v
[True, False, True, ...]

a < 10
    |
    v
[True, True, False, ...]
```

Then NumPy overloads `&` to combine those arrays element by element.

This works because `&` is an overloadable operator.

By contrast:

```python
(a > 0) and (a < 10)
```

does not mean element-wise conjunction.

Python's `and` first asks for the truth value of the entire left-hand object.

For a multi-element NumPy array, that truth value is ambiguous: should the array count as true if every element is true, or if at least one element is true?

NumPy therefore rejects that interpretation rather than guessing.

This reveals an important distinction:

```text
and
    short-circuiting
    special language-level expression
    operates on the truthiness of whole objects
    not overloadable

&
    eager operand evaluation
    ordinary overloadable operator
    can be given element-wise semantics by libraries
```

The same principle applies to pandas Boolean masks.

### A Consequence of Eager Operand Evaluation

One observable consequence is that both expressions are evaluated regardless of the first result.

```python
def check_a():
    print("A checked")
    return False

def check_b():
    print("B checked")
    return True

result = check_a() & check_b()
```

Output:

```text
A checked
B checked
```

With short-circuit evaluation:

```python
result = check_a() and check_b()
```

Output:

```text
A checked
```

`check_b()` would never run because `check_a()` returned `False`.

---

If both operations must happen independently, make that intention explicit:

```python
a = check_a()
b = check_b()

result = a and b
```

That is generally clearer than relying on the evaluation behavior of a bitwise operator for side effects.

---

## Takeaway

Use `and` and `or` for normal Python conditional logic:

```python
condition_a and condition_b
```

They short-circuit and are built into Python's control-flow semantics.

Use `&` and `|` primarily for:

- bitwise operations,
- bit flags,
- overloaded element-wise operations such as NumPy and pandas.

Do not normally use `&` or `|` merely because you want both expressions to execute. If both computations must happen, evaluate them explicitly.

Most importantly:

> `&` and `|` are ordinary overloadable binary operators whose operands are evaluated according to Python's normal eager expression semantics.

> `and` and `or` are special language constructs whose evaluation semantics allow short-circuiting.

That distinction between **operator meaning**, **operator overloading**, and **evaluation strategy** is the important computer-science idea underneath the syntax.

---

[^1]: **Ada provides a clear example of eager versus short-circuit logical evaluation.** Its regular logical operators, `and` and `or`, evaluate both operands, while `and then` and `or else` are the short-circuit forms:

    ```ada
    A and B          -- both operands are evaluated
    A and then B     -- B is evaluated only if A is True

    A or B           -- both operands are evaluated
    A or else B      -- B is evaluated only if A is False
    ```

    This demonstrates that the logical operation being represented and the strategy used to evaluate its operands are separate language-design decisions.

