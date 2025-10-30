---
math: true
title: Suppose Not draft 2 (Not Not So Fast)
date: 2025-10-27
categories: [Mathematics, Proof theory]
tags: [logic, concreteness, contradiction]     # TAG names should always be lowercase
image:
  path: assets/img/Lightning bolt.png
---

--> alternative post title: "Not Not So Fast"

When $$\neg S$$ leads to a contradiction ($$\bot$$) does that imply that $$S$$ must be true?, that is

$$
(\neg S \Rightarrow \bot) \Rightarrow S.
$$

---

In **classical mathematics**, we often rely on the rule:

$$
\neg\neg S \Rightarrow S
$$

If assuming that a statement $$\neg S$$ is true leads to a contradiction $$\bot$$, then we conclude that $$S$$ must be true. Note that the antecedent
$$(\neg S \Rightarrow \bot)$$
*is just* $$\neg\neg S$$ (since $$\neg S \equiv S\Rightarrow\bot$$). So the step to $$S$$ here is exactly **double negation elimination** (DNE). This inference is not forced on us by “the nature of mathematics”; it is licensed by the **logical axioms** we adopt. In particular, classical logic assumes:

1. The **law of non-contradiction (LNC)** — also valid intuitionistically:
   $$
   \neg (S \land \neg S)
   $$

2. The **law of excluded middle (LEM)**:
   $$
   S \lor \neg S
   $$

3. **Double negation elimination (DNE)**:
   $$
   \neg \neg S \Rightarrow S
   $$

Over the intuitionistic base, LEM and DNE are **interderivable**; accepting either (or equivalents such as Peirce’s law, consequentia mirabilis, the classical dilemma, etc.) recovers classical reasoning.

> A small but important clarification about “proof by contradiction.”  
> English uses that phrase for two patterns:
> - **Negation introduction (intuitionistically valid):** assume \(S\), derive \(\bot\), conclude \(\neg S\).  
> - **Reductio to the positive (classically valid):** assume \(\neg S\), derive \(\bot\), conclude \(S\) — this uses DNE/LEM.

  
## Different Rules

In **intuitionistic logic**[^1], the situation changes. The inference

$$
(\neg S \Rightarrow \bot) \Rightarrow S
$$

is not automatically valid, because that is precisely DNE. One can derive only:

$$
(\neg S \Rightarrow \bot) \Rightarrow \neg \neg S.
$$

Thus, the failure of $$\neg S$$ does not directly produce the truth of $$S$$. Instead, it tells us that a counterexample to $$S$$ cannot be constructed—a weaker form of certainty in this framework. (In many everyday cases—e.g., when \(S\) is **stable** or built from **decidable** predicates—classical reductio can be converted to constructive evidence, but not in full generality.)

## Commitment to Logic

Mathematics does not prove the reliability of its own strongest foundations from *within* those foundations. More precisely, by **Gödel’s second incompleteness theorem**, no sufficiently strong, effectively axiomatized, **consistent** theory \(T\) (such as PA or ZFC) can prove its own consistency \(\mathsf{Con}(T)\). We can—and do—prove **relative** consistency results (consistency of weaker systems in stronger meta-theories), but not a theory’s *own* consistency from inside itself.

Within classical (and intuitionistic) *explosive* logics, if a contradiction were discovered, then by the **principle of explosion**[^2] any statement $$S$$ would become provable, trivializing the system. (Some alternative, **paraconsistent** logics block explosion and study contradictions without collapse; classical mathematics does not take this route.) 

This means that proof by contradiction is not only a reasoning tool. It is a commitment. We accept it because we accept the system that validates it.

## A Conditional Certainty

The conclusion is not that proof by contradiction is flawed, but that it makes explicit the dependency of mathematical truth-claims on the logical framework we choose. What counts as a **valid proof** is not universal; it is shaped by the axioms and inference rules that define reasoning itself. Model-theoretically, “truth” is evaluated relative to axioms and semantics; what varies with logic is which inferences count as evidence for that truth.

$$
\begin{gathered}
\text{"Mathematics may look complete and exact only because we }\\
\text{accept the rules that make it seem so."}
\end{gathered}
$$

---

[^1]: Intuitionistic logic validates LNC and rejects unrestricted LEM and DNE; it understands truth as the existence of a construction (proof) rather than mere non-refutability.

[^2]: Also called *ex falso quodlibet*: from \(S \land \neg S\) one can derive any \(T\). Classical and intuitionistic logics validate explosion; **paraconsistent** logics are designed to reject it.


# References


- [Logic and Classical vs. Intuitionistic Logic](https://plato.stanford.edu/entries/logic-classical/)

- [Gödel’s Incompleteness Theorems](https://plato.stanford.edu/entries/goedel-incompleteness/)

- https://plato.stanford.edu/entries/logic-classical/

- https://plato.stanford.edu/archives/sum2014/entries/logic-intuitionistic/

- https://plato.stanford.edu/entries/goedel-incompleteness/

- https://en.wikipedia.org/wiki/Double_negation

- https://en.wikipedia.org/wiki/Law_of_excluded_middle

- https://en.wikipedia.org/wiki/Law_of_thought

- https://en.wikipedia.org/wiki/Intuitionistic_logic

- https://en.wikipedia.org/wiki/Principle_of_explosion


# Further Reading


- 

