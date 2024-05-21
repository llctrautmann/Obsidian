---
title: Fundamental Theorem of Calculus
date: 06-11-2023
time: 19:50
author: Luca Trautmann
tags:
  - Mathematics
series: Probability Theory
chapter: 12
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Fundamental Theorem of Calculus

The Fundamental Theorem of Calculus bridges the concepts of differentiation and integration, two core operations in calculus. It is divided into two parts:

## Part 1: The First Fundamental Theorem of Calculus

The First Fundamental Theorem of Calculus states that if a function `f` is continuous on the closed interval `[a, b]` and `F` is the indefinite integral of `f` on `[a, b]`, then `F` is differentiable on the open interval `(a, b)`, and `F'` (the derivative of `F`) is equal to `f`.

Mathematically, it is expressed as:

$$ F'(x) = f(x) $$

Where:
- `F'(x)` is the derivative of `F`
- `f(x)` is a continuous function on `[a, b]`

## Part 2: The Second Fundamental Theorem of Calculus

The Second Fundamental Theorem of Calculus provides an efficient method for evaluating definite integrals. It states that if `f` is a continuous function on `[a, b]` and `F` is an antiderivative of `f` on `[a, b]`, then the definite integral of `f` from `a` to `b` is equal to `F(b) - F(a)`.

Mathematically, it is expressed as:

$$ \int_{a}^{b} f(x) \, dx = F(b) - F(a) $$

Where:
- `\int_{a}^{b} f(x) \, dx` is the definite integral of `f` from `a` to `b`
- `F(a)` and `F(b)` are the values of an antiderivative `F` of `f` at `a` and `b` respectively.

### Conclusion

The Fundamental Theorem of Calculus is a powerful tool in calculus, linking the concept of integration (finding the area under a curve) with differentiation (finding the rate of change). Its implications are far-reaching in various fields of mathematics and applied sciences.













