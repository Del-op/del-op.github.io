---
math: true
title: How Formal Language Makes Patterns Reusable
date: 2026-08-03
categories: [Mathematics, Logic]
tags: [syntax, semantics]
image:
  path: assets/posts-covers/begriffsschrift-white.png

---

Abstraction, syntax, and semantics.

I have two thoughts in mind:

- Two people may use different symbols, languages, or mental models while appearing to represent the same underlying pattern.
- Without some reusable representational system, it is difficult to treat concrete cases systematically as instances of a common pattern.

These two thoughts become more precise once we distinguish an abstract structure, a formal expression, and an interpretation of that expression.

## Concrete Events & Abstract Forms

Suppose someone combines two oranges with three oranges and counts five oranges. Somewhere else, someone combines five apples with four apples and counts nine apples.

As physical events, these situations are different. They involve different objects, quantities, places, and times. Yet arithmetic ignores most of those differences. It preserves only an invariant pattern:

$$
\text{size of the combined collection}
=
\text{size of first}
+
\text{size of second}.
$$

Treating both events as instances of this pattern is an act of abstraction. We disregard the kind, color, weight, location, and other features of the objects while preserving their cardinality and the way the collections are combined.

Once this structure has been isolated, we can express it using a common form:

$$
c = m+n.
$$

The variables do not belong to oranges, apples, or any particular object. They provide reusable positions within a pattern that can be instantiated by many different events.

But there are also hidden assumptions in the previous example for the abstraction to work:

- the collections are disjoint;
- no object appears or disappears;
- each object remains individually countable;
- the identity of the objects is irrelevant to the question.

If two drops of water are combined, they may become one larger drop. If two groups overlap, adding their sizes double-counts the shared members. If objects are created or destroyed during the process, the result may no longer equal the sum of the original quantities.

The physical act of “putting together” is therefore not intrinsically addition. It becomes a model of addition only after we choose what is being counted, which properties are relevant, and which assumptions are being imposed.

The process is better represented as:

$$
\text{concrete event}
\xrightarrow{\text{abstraction}}
\text{mathematical structure}
\xrightarrow{\text{representation}}
\text{syntactic expression}.
$$

This also explains how abstraction compresses experience. Instead of storing every event independently, we represent a general type and treat particular events as its instances.

But this compression can be misleading. Abstraction gives us power precisely because it discards information; that is also why abstraction can fail us if used carelessly.

## Syntax and Semantics Are Not One-to-One

The expressions

$$
m+n,
\qquad
+(m,n),
\qquad
\operatorname{add}(m,n)
$$

have different visible forms, but they may represent the same operation and yield the same result when their variables receive the same values.

Shared mathematical content therefore does not require shared notation.

That was an example of having different expressions, but the same interpretation.

The opposite can happen too. The same expression can receive different interpretations.

In ordinary arithmetic,

$$
2+3=5.
$$

In arithmetic modulo $$4$$,

$$
\begin{aligned}
2+3 &= 5 \\
    &\equiv 1 \pmod 4.
\end{aligned}
$$

The expression does not carry one complete meaning by itself. Its interpretation depends on the structure in which it is evaluated.

The numerals also depend on interpretation. The symbol $$2$$ may refer to the natural number $$2$$, an equivalence class modulo $$4$$, a real number, or some other object in a formal structure.

## Making Relations Explicit

Without a formal representational system, reality would not lose its relations. 

But these relations would remain difficult to isolate, communicate, combine, and test.

What representation does is make a proposed relation explicit and available for inference. 

Together, abstraction and representation allow us to move from 

$$
\text{this particular event}
$$

to:

$$
\text{every event of this form}.
$$

Two events, however, are rarely simply identical. They are treated as equivalent relative to a structure an abstraction preserves.

## What Formalization Makes Possible

Abstraction selects a common structure by ignoring certain differences.

A formal language provides expressions with which that structure can be represented.

Syntax determines how those expressions are formed.

Semantics determines the meaning of expressions relative to a structure.

Together, these capacities allow a finite mind to reason about indefinitely many possible cases.

That power always has conditions. To use a formal pattern responsibly, we must ask what the abstraction preserves, what it ignores, how the resulting structure is represented, and under which interpretations the representation remains faithful.


# Further Reading

- [Classical Logic — Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/logic-classical/){:target="_blank"}
- [Introduction to First-Order Logic — Open Logic Project](https://builds.openlogicproject.org/content/first-order-logic/introduction/introduction.pdf){:target="_blank"}
