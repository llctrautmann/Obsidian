---
title: Probability Density Functions Definition
date:
  - 01-01-2024
time: 18:11
author: Luca Trautmann
tags: 
series: Probability Theory
chapter: "15"
modified: 2024-05-06
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Probability Density Functions Definition

A probability density function (or simply density function) is a function that maps a point $\mathbf{x}$ in the sample space to a number between 0 and 1 . 

The integral of the density function over all points in the sample space must equal 1 , so that it is a well-defined probability distribution.

A function $f: \mathbb{R}^D \rightarrow \mathbb{R}$ is called a probability density function (PDF) if
1. $\forall x \in \mathbb{R}^D: f(x) \geqslant 0$
2. Its integral exists and
$$
\int_{\mathbb{R}^D} f(\boldsymbol{x}) \mathrm{d} \boldsymbol{x}=1
$$









