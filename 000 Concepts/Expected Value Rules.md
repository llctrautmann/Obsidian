---
title: Expected Value Rules
date: 22-05-2023
time: 13:16
author: Luca Trautmann
tags: []
series: "Probability Theory"
chapter: 9
---

# Expected Value Rules
## Linearity of Expected Values
The Linearity of Expectation is a fundamental concept in probability theory. It states that the expected value of the sum of two or more random variables is equal to the sum of their individual expected values. The Linearity of Expectation can be written as:

$$\mathbb{E}[X+Y] = \mathbb{E}[X] + \mathbb{E}[Y]$$

The same holds for multiplication which results in the following:

$$\mathbb{E}[aX + b] = a \mathbb{E} [X] + b$$

where $\mathbb{E}$ denotes the expected value, and $X$ and $Y$ are two random variables. This formula can be extended to more than two random variables as follows:

$$\mathbb{E}[X_1 + X_2 + \cdots + X_n] = \mathbb{E}[X_1] + \mathbb{E}[X_2] + \cdots + \mathbb{E}[X_n]$$

where $X_1, X_2, \cdots, X_n$ are $n$ random variables. This leads to the following generalisations:

$$
\mathbb{E}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n \mathbb{E}\left[X_i\right]
$$

If they are independent, the expectation of their product is given by

$$
\mathbb{E}\left[\prod_{i=1}^n X_i\right]=\prod_{i=1}^n \mathbb{E}\left[X_i\right]
$$


## Sum and Product of Variances
For multiple random variables the sum variance of all random variables is the sum of the individual variances:
$$
\mathbb{V}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n \mathbb{V}\left[X_i\right]
$$
The variance of their product can also be derived, as follows:
$$
\begin{aligned}
\mathbb{V}\left[\prod_{i=1}^n X_i\right] & =\mathbb{E}\left[\left(\prod_i X_i\right)^2\right]-\left(\mathbb{E}\left[\prod_i X_i\right]\right)^2 \\
& =\mathbb{E}\left[\prod_i X_i^2\right]-\left(\prod_i \mathbb{E}\left[X_i\right]\right)^2 \\
& =\prod_i \mathbb{E}\left[X_i^2\right]-\prod_i\left(\mathbb{E}\left[X_i\right]\right)^2 \\
& =\prod_i\left(\mathbb{V}\left[X_i\right]+\left(\mathbb{E}\left[X_i\right]\right)^2\right)-\prod_i\left(\mathbb{E}\left[X_i\right]\right)^2 \\
& =\prod_i\left(\sigma_i^2+\mu_i^2\right)-\prod_i \mu_i^2
\end{aligned}
$$

# Chapters
```dataview
TABLE chapter as Chapter
FROM "Concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
