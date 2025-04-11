---
math: true
title: Induction
date: 2025-04-10
categories: [Mathematics, proof theory]
tags: [math]     # TAG names should always be lowercase
image:
  path: assets\posts-covers\dominos-cropped.png
---

**Mathematical induction** is a method for **proving** that a statement $$P(n)$$ is true for every **Natural number** $$n$$, that is, that the infinitely many cases $$P(0),P(1),P(2),P(3),\dots$$ all hold. This is done by first proving a simple case, then also showing that if we assume the claim is true for a given case, then the next case is also true.

![dominos](assets/img/220px-Dominoeffect.png)  

$$
\begin{gather*}
\small \text{Mathematical induction can be informally illustrated by reference} \\
\small \text{to the sequential effect of falling dominoes.} \\
\end{gather*}
$$

A **proof by induction** consists of two cases. The first, the **base case**, proves the statement for $$n=0$$ without assuming any knowledge of other cases. The second case, the **induction step**, proves that if the statement holds for any given case $$n=k$$, then it must also hold for the next case $$n=k+1$$. These two steps establish that the statement holds for every natural number $$n$$. The base case does not necessarily begin with $$n=0$$, but often with $$n=1$$, and possibly with any fixed natural number $$n=N$$, establishing the truth of the statement for all natural numbers $$n\geq N$$.

Despite its name, mathematical induction differs fundamentally from [inductive reasoning](https://en.wikipedia.org/wiki/Inductive_reasoning){:target="_blank"} as [used in philosophy](https://en.wikipedia.org/wiki/Problem_of_induction "Problem of induction"){:target="_blank"}, in which the examination of many cases results in a probable conclusion. The mathematical method examines infinitely many cases to prove a general statement, but it does so by a finite chain of [deductive reasoning](https://en.wikipedia.org/wiki/Deductive_reasoning){:target="_blank"} involving the variable $$n$$, which can take infinitely many values. The result is a rigorous proof of the statement, not an assertion of its probability.


## proof steps:

1. The **base case** (or **initial case**): prove that the statement holds for 0, or 1 (or any fixed natural number $$N$$).
2. The **induction step** (or **inductive step**, or **step case**): prove that for every $$n$$, if the statement holds for $$n$$, then it holds for $$n+1$$. In other words, assume that the statement holds for some arbitrary natural number $$n$$, and prove that the statement holds for $$n+1$$.

The hypothesis in the induction step, that the statement holds for a particular $$n$$, is called the **induction hypothesis** or **inductive hypothesis**. To prove the induction step, one assumes the induction hypothesis for $$n$$ and then uses this assumption to prove that the statement holds for $$n+1$$.

# References

[Mathematical induction Wikipedia](https://en.wikipedia.org/wiki/Mathematical_induction){:target="_blank"}
