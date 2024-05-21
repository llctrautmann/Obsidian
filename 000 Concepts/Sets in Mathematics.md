---
title: Sets in Mathematics
date: 19-06-2023
time: 19:17
author: Luca Trautmann
tags:
  - Mathematics
series: Mathematics & Statistics
chapter: 6
modified: 2024-02-10
---

# Sets in Mathematics
Sets are fundamental concepts in mathematics and are used in various advanced mathematical concepts. A set is an unordered collection of distinct objects, called elements or members. Sets are denoted by uppercase letters (e.g., A, B, C), and the elements of a set are denoted by lowercase letters (e.g., a, b, c).

Sets can be defined explicitly by listing their elements or implicitly by specifying a property that the elements must satisfy. The order of elements in a set does not matter, but it is preferred to write them in a specific order for clarity.

The cardinality of a set refers to the number of elements it contains and is denoted by |S|. Set membership is denoted by the symbol "∈" and indicates that an element belongs to a set. Conversely, the symbol "∉" denotes that an element does not belong to a set.

Example:

Consider the set $S = {a, b, c}$ This set has a cardinality of 3 $(|S| = 3)$. The element a belongs to the set $(a ∈ S)$, while the element d does not belong to the set $(d ∉ S)$.

Set builder notation is used when it is impractical to list all the elements explicitly. It involves describing the set based on shared properties of its elements. For instance, the set of real numbers less than 5 can be represented as $S = {x: x < 5}$, where x is an element that satisfies the condition x < 5.

## Set equality

Two sets are considered **equal** if and only if they contain the exact same elements. This relationship is denoted as A=B

. Conversely, if two sets are not equal, the relationship is denoted as A≠B.

## Sets contain unique elements

By definition, a set contains distinct elements. Having duplicates in a set is meaningless because of the definition of set equality.

Consider the sets A={1,1,2,3}

and B={1,2,3}. Two sets are considered equal if they contain the same elements. Because any element in A is also in B, it is the case that A=B.

In this example, the duplicates in the set A

were shown to explain the futility of a set with repetitions, since it turns out to be equal to another without them. **Multi-sets** are a general concept that allow for repetitions. A would be considered a multi-set in this case.






# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```