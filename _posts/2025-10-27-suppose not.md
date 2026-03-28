---
math: true
title: Suppose Not
date: 2025-10-28
categories: [Mathematics, Proof theory]
tags: [logic, philosophy, proof]     # TAG names should always be lowercase
image:
  path: assets/posts-covers/Lightning bolt - B&W.png
---

## Statement

When $$\neg S$$ leads to a contradiction $$\bot$$ does that imply that $$S$$ must be true? That is,


$$

(\neg S \to \bot) \to S.

$$

This formula is equivalent to the rule of double negation elimination.

---

In **classical mathematics**, we often rely on the rule:

$$

\begin{gathered}
\neg \neg S \to S
\end{gathered}

$$

If assuming that a statement $$\neg S$$ is true leads to a contradiction $$\bot$$, then we conclude that $$S$$ must be true. This inference is a logical principle, accepted in classical logic but not in all systems. It is grounded in the **logical principles**[^1]we adopt. In particular, classical logic validates:

1. The **law of non-contradiction (LNC)**:  (derivable intuitionistically)

   $$
   \neg (S \land \neg S)
   $$

2. The **law of excluded middle (LEM)**:  

   $$

   \begin{gathered}
   S \lor \neg S
   \end{gathered}
   
   $$

3. **Double negation elimination (DNE)**:  

   $$
   \neg \neg S \to S
   $$

Over the intuitionistic base, LEM and DNE are **interderivable**; accepting either (or equivalents such as Peirce’s law, consequentia mirabilis, etc.) recovers classical reasoning.

  
## Different Rules

In **intuitionistic logic**[^2], the situation changes. The inference 

$$(\neg S \to \bot) \to S$$

 is not automatically valid. Instead:

$$

(\neg S \to \bot) \equiv \neg \neg S

$$

Thus, the refutation (falsity) of $$\neg S$$ does not directly produce the truth of $$S$$. Instead, it shows that no counterexample to $$S$$ can be constructed, which is a weaker form of certainty[^3].


## Commitment to Logic

We assume our foundational theories are consistent, i.e. free of contradiction. If a contradiction were found, then due to the **principle of explosion**[^4], any statement would become provable, and the entire theory (formulated in explosive logics) would collapse into triviality.

A proof by contradiction is not a self-evident act of reason, but an act of trust in the logical system that validates it.


## A Conditional Certainty

The conclusion is not that proof by contradiction is flawed, but that it makes explicit the dependency of mathematical truth on the logical framework we choose. What counts as a **valid proof** is not universal; it is shaped by the axioms that define reasoning itself. Mathematics is not absolute but conditional on the structure of thought and logic that underlies it.

$$

\begin{gathered}

\text{"Mathematics may look complete and exact only because we }\\

\text{choose the rules that make it seem so."}

\end{gathered}

$$


# References

- [Classical Logic (Stanford Encyclopedia of Philosophy)](https://plato.stanford.edu/entries/logic-classical/){:target="_blank"}

- [Intuitionistic Logic (Stanford Encyclopedia of Philosophy)](https://plato.stanford.edu/entries/logic-intuitionistic/){:target="_blank"}

- [Gödel’s Incompleteness Theorems (Stanford Encyclopedia of Philosophy)](https://plato.stanford.edu/entries/goedel-incompleteness/){:target="_blank"}

- [Principle of explosion - Wikipedia](https://en.wikipedia.org/wiki/Principle_of_explosion){:target="_blank"}


# Further Reading


- [Lectures on the Curry-Howard Isomorphism](https://disi.unitn.it/~bernardi/RSISE11/Papers/curry-howard.pdf){:target="_blank"}

- [Teach Yourself Logic by Peter Smith](https://www.logicmatters.net/resources/pdfs/LogicStudyGuide.pdf){:target="_blank"}

- Dummett, M. *Elements of Intuitionism*


---

[^1]: Presented either as logical axiom schemata or as rules of inference.


[^2]: Intuitionistic logic does not accept LEM (and, equivalently, double-negation elimination) in general. It keeps the usual structural rules (e.g., modus ponens, non-contradiction, explosion) but interprets truth via proof/constructive evidence.


[^3]: $$S$$ is strictly stronger than $$\neg \neg S$$ intuitionistically: from $$S$$ we can deduce $$\neg \neg S$$, but the other way around is not derivable.


[^4]: From a contradiction, any statement follows. Hence, in an explosive logic, any inconsistent theory is trivial; every sentence is provable (a collapse of provability). Paraconsistent logics avoid this by rejecting explosion.