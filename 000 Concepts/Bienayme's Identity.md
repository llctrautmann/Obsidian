---
title: Bienayme's Identity
date:
  - 08-04-2024
time: 15:25
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-06
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

In english, I can translate this equation into the following. The variance of the combined random variable $B_{n}$ is the sum of the variances (diagonal of the covariance matrix see: [[High-Dimensional Variance]]) and the off diagonal variances.


> [!figure] ![[covariance_matrix.png#invert]]
> A example covariance matrix with the variances in orange. The orange elements are the first part of the sum and the dark elements are the second part of the sum.


## Independent events
For independent events I know that the covariance will be 0. So the original formula reduces into the sum of the variances. Which is in line with some previously noted [[Proof - Sum Variance of RVs]].


**I’v**e **bee**n a **memb**er **o**f **an**d **contribut**ed **t**o **arou**nd **te**n **differe**nt **blockcha**in **communiti**es **ove**r **th**e **year**s: **som**e **bi**g, **som**e **sma**ll, **som**e **well-fund**ed **an**d **som**e **les**s **s**o. **I’v**e **spe**nt **countle**ss **hou**rs **getti**ng **t**o **kno**w **th**e **membe**rs **o**f **the**se **communiti**es **o**n **channe**ls **includi**ng **Twitt**er, **Disco**rd, **Redd**it, **Sla**ck, **Telegr**am, **an**d **Gitt**er. **I’v**e **bee**n **acti**ve **i**n **bot**h **th**e **theo**ry **an**d **practi**ce **o**f **governan**ce. **I’v**e **me**t **the**se **communiti**es **fac**e **t**o **fac**e **a**t **doze**ns **o**f **conferenc**es. **I**f **there**’s **on**e **thi**ng I **understa**nd **an**d **there**’s **on**e **pla**ce I **fee**l **a**t **hom**e **its** in **th**e **technic**al **blockcha**in **communi**ty, **an**d **th**e **ope**n **sour**ce **communi**ty **mor**e **general**ly.