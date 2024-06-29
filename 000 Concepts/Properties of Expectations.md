---
title: Properties of Expectations
date:
  - 28-11-2023
time: 16:22
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
chapter: 10
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "Concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Properties of Expectations
The expectation of a random variable $X$ has the following properties:

(i) __Function__. For any function $g$,

$$
\mathbb{E}[g(X)]=\sum_{x \in X(\Omega)} g(x) p_X(x) .
$$

(ii) __Linearity__. For any function $g$ and $h$,

$$
\mathbb{E}[g(X)+h(X)]=\mathbb{E}[g(X)]+\mathbb{E}[h(X)]
$$

(iii) __Scale__. For any constant c,

$$
\mathbb{E}[c X]=c \mathbb{E}[X]
$$


(iv) __DC Shift__. For any constant c,

$$
\mathbb{E}[X+c]=\mathbb{E}[X]+c
$$

The same applies for continuous random variables.










