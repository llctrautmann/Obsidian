---
title: Bienayme's Identity
date:
  - 08-04-2024
time: 15:25
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-04-08
---
# Bienayme's Identity
In probability theory, Bienaymé's identity is a formula for the variance of random variables which are themselves sums of random variables. I provide a little intuition for the identity and then prove it.

## Intuition
Let $B_n$ be a random variable which is itself a sum of random variables:

$$
B_{n} := \sum^n_{i=1} X_{i}
$$
[[Bienayme's Identity]] states that the variance of $B_{n}$ is:

$$\color{orange}
\mathbb{V}\left[B_n\right]=\sum_{i=1}^n \mathbb{V}\left[X_i\right]+\sum_{i, j=1, i \neq j}^n \operatorname{cov}\left[X_i, X_j\right]
$$

In english, I can translate this equation into the following. The variance of the combined random variable $B_{n}$ is the sum of the variances (diagonal of the covariance matrix [[High-Dimensional Variance]])
