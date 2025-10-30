---
math: true
title: Suppose Not draft 1 (Not Not So Fast)
date: 2025-10-26
categories: [Mathematics, Proof theory]
tags: [logic, concreteness, contradiction]     # TAG names should always be lowercase
image:
  path: assets/posts-covers/Lightning bolt - B&W.png
---

--> alternative post title: "Not Not So Fast"

In **classical mathematics**, we often rely on the rule:

$$
\neg\neg S \to S
$$

If assuming that a statement $$\neg S$$ is true leads to a contradiction $$\bot$$, then we conclude that $$S$$ must be true. This is the structure behind a **proof by contradiction**.

This inference is not derived from the nature of mathematics itself. It is grounded in the **logical axioms** we adopt. In particular, classical logic assumes:

1. The **law of non-contradiction**:  

   $$
   \neg (S \land \neg S)
   $$

2. The **law of excluded middle (LEM)**:  

   $$
   S \lor \neg S
   $$

3. **Double negation elimination**:  

   $$
   \neg \neg S \Rightarrow S
   $$

These principles are **equivalent in strength** to reductio ad absurdum (RAA).

---

## A Different Perspective

In **intuitionistic logic**, the situation changes. The inference

$$
(\neg S \Rightarrow \bot) \Rightarrow S
$$

is not automatically valid. One can derive only:

$$
(\neg S \Rightarrow \bot) \Rightarrow \neg \neg S
$$

Thus, the failure of $$\neg S$$ does not directly produce the truth of $$S$$. Instead, it reveals a lack of a counterexample, which is a weaker form of certainty.

This difference reflects a deeper philosophical concern:  
Is truth a binary assignment, or does it require construction and explicit realization?

---

## The Trust We Place in Logic

Mathematics does not prove the reliability of its own foundation. Classical logic is **assumed** consistent, but according to **Gödel’s second incompleteness theorem**, a system that is expressive enough for arithmetic cannot prove its own consistency.

We trust that no contradiction lies hidden within our foundation. If a contradiction were discovered in classical logic or in systems like ZFC set theory, then due to the **principle of explosion**:

$$
(S \land \neg S) \Rightarrow T
$$

any statement $$T$$ would become provable, and the entire mathematical structure would collapse into triviality.

This means that proof by contradiction is not only a reasoning tool. It is a commitment. We accept it because we accept the system that validates it.

---

## A Conditional Certainty

The conclusion is not that proof by contradiction is flawed, but that it makes explicit the dependency of mathematical truth on the logical framework we choose. What counts as a valid proof is not universal. It is shaped by the axioms that define the boundaries of reasoning itself.

This reveals a philosophical point:  
Mathematical truth is not absolute. It is conditional on the structure of thought that underlies mathematics. What is a theorem in one logical world might remain unknowable in another.

Mathematics may look complete and exact only because we accept the rules that make it look so.

---

## References


## Further Reading

- 

