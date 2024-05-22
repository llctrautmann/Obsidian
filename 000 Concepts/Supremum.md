---
title: Supremum
date:
  - 22-05-2024
time: 16:39
author: Luca Trautmann
tags:
  - Mathematics
series: Mathematics & Statistics
type: Concept
formula: 
modified: 2024-05-22
---
# Supremum
The **supremum** (often abbreviated as **sup**) of a set is the least upper bound of that set. It is a concept from real analysis that generalizes the notion of the maximum of a set.

Here’s a more detailed explanation:

- **Upper Bound**: A number \( u \) is an upper bound of a set \( S \) if every element \( s \) in \( S \) satisfies \( s \leq u \).

- **Least Upper Bound (Supremum)**: The supremum of a set \( S \), denoted as \( \sup(S) \), is the smallest number that is an upper bound of \( S \). In other words, it is the smallest number \( u \) such that \( s \leq u \) for all \( s \in S \), and for any number \( v \) less than \( u \), there exists some \( s \in S \) such that \( s > v \).

### Examples

1. **Finite Set**: For the set \( S = \{1, 2, 3\} \), the supremum is \( \sup(S) = 3 \), which is also the maximum of the set.

2. **Infinite Set**: For the set \( S = \{ x \in \mathbb{R} \mid 0 \leq x < 1 \} \), the supremum is \( \sup(S) = 1 \). Note that 1 is not an element of the set, but it is the least upper bound.

3. **Unbounded Set**: For the set \( S = \{ x \in \mathbb{R} \mid x > 0 \} \), the supremum does not exist in the real numbers because the set is unbounded above.

### Usage in Functions

In the context of functions, the supremum is often used to describe the maximum value a function can take over a certain interval. For example, for a continuous function \( f \) on the interval \([a, b]\), the supremum of \( f \) is given by:

\[ \sup_{x \in [a, b]} f(x) \]

This represents the least upper bound of the values of \( f(x) \) for \( x \) in the interval \([a, b]\). If \( f \) attains its maximum value at some point in \([a, b]\), then the supremum is equal to this maximum value.