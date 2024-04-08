---
title: Inverse Fallacy
date: 01-09-2023
time: 18:03
author: Luca Trautmann
tags: ["Statistics"]
series: Probability Theory
chapter: 
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Inverse Fallacy
Recall the proof of the inverse probability rule, <mark style="background: #FFB8EBA6;">a trivial reformulation of the product rule</mark>. For any nonzero probability event $\mathrm{H}$ and D:

- $P(H$ and $D)=P(D$ and $H)$ (product of probabilities commute)
- $P(H \mid D) \times P(D)=P(D \mid H) \times P(H)$ (applying product rule to both sides)
- $P(H \mid D)=P(D \mid H) \times P(H) / P(D)$ (the inverse probability rule)

Note that joint probabilities, the product of two probabilities, commute-i.e., the order of the individual probabilities does not change the result of their product:
$$
P(H \text { and } D)=P(D \text { and } H)
$$
As you can see from the last equation, conditional probabilities do not commute:
$$
P(H \mid D) \neq P(D \mid H)
$$










