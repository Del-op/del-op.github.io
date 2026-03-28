---
math: true
title: When Order Looks Random
date: 2025-09-19
categories: [Mathematics, Information theory]
tags: [randomness, pattern, complexity]     # TAG names should always be lowercase
image:
  path: assets/posts-covers/When Order Looks Random.png
---

I’ve been thinking about randomness and patterns, and I don’t fully agree with the idea that patterns are universal independent entities. For us humans, something like:<br>
<span class="d-block text-center">`1, 2, 3, 4, 5, 6, 7, 8, 9,…`</span>
is very obviously a pattern. It feels simple and intuitive because we can decode it as: “start from 1 and increment by 1 for each step”. But that’s our way of decoding. It’s easy for us because our way of thinking includes counting, addition, and repetition as natural tools.

But this doesn't have to be universal. Maybe another kind of mind doesn’t have “+1” as a basic operation. For them, the sequence might not look like a pattern at all. On the other hand, something that looks completely random to us could be perfectly ordered for them with a different kind of decoding that matches it.

This means that when we say “this is a pattern”, we’re actually being biased by the way we think. We call certain things patterns because they are easy for us to describe, and another mind, describing the world differently, might not see the pattern, and even find patterns where we see none.

I do agree that patterns exist in the general sense, that there exists encodings of information into simple patterns, and such encodings could be shared universally, but the way they are recognized or felt depends on the decoding language we have, and it could happen that the language or mind be incapable of acquiring a specific decoding due to its construction. For humans, the cognitive primitives are possibly operations like “+1”, “repeat”, “mirror”, etc. That’s why sequences like `1,2,3,4,5` feel very simple. But if you don’t have those operations, it’s not obvious anymore. Instead, they become random, unless there is another decoding that could describe the same pattern in a simple form.

This connects with the idea of **Kolmogorov complexity**, which basically says that the complexity of a sequence is the length of the shortest algorithmic description that generates it (like a piece of code). For us, “1,2,3,4,5,...” could be described with a very short description, so we call it simple. It also says that a random-looking sequence is one that has no shorter description than itself (e.g., the binary result of flipping a fair coin many times: 01101001...). There is no formula or shortcut. To describe the output, we quite literally have to "spit it out", so we call it random. But the key is that what counts as a “short description” depends on the description tools we allow. Our “short” is based on human primitives. Another mind could have different primitives (maybe they could have built-in primitives for describing what we view as random), which means their idea of what’s simple or random could be completely different.

To me, randomness and patterns are not absolute. There is structure out there, some underlying uniqueness, but whether it shows up as an “obvious pattern” or not depends on the way we think, and the language we use to decode it. Our sense of order is biased, and what feels like noise to us might be a clear, simple pattern to someone else.


# References

-

# Further Reading

- [kolmogorov complexity by bruno durand and Alexander Zvonkin](https://www.labri.fr/perso/zvonkin/Research/kolmathan.pdf){:target="_blank"}