---
title: Moments of a Distribution
date:
  - 20-05-2023
time: 18:08
author: Luca Trautmann
tags: 
series: Probability Theory
chapter: 7
modified: 2024-07-01
---

# Moments of a Distribution
## Introduction
Moments of a distributions are the summary statistics that can be collected from it. Most notably are the expected value $(\mathbb{E})$, variance $(\mathbb{V})$, median and mode. 

## First Moment
The mean of a distribution is defined in two ways depending on whether the random variable is continuous or discrete. 

For discrete variables:
$$\mathbb{E}[X] = \sum_{x \in X} x \times p(x) $$
For continuous random variables:
$$\mathbb{E}[X] = \int_X x \times p(x) dx$$
For a function $g(x)$ that is applied to a random variable. The expectation is given by:

$$\mathbb{E}[X] = \int_X g(x) \times p(x)$$
Other rules apply to the expected value. 

>[!Example]-
> __Discrete random variable__
> First, let's define a discrete random variable $X$ that can take the values of $S = \{1, 2, 3\}$ with corresponding probabilities of $p(X) = \{0.2, 0.3, 0.5\}$ respectively. 
> 
> Then, the expected value ($\mathbb{E}[X]$) for the discrete random variable X is calculated as:
> 
> $$\mathbb{E}[X] = \sum_{x \in X} x \cdot P(X = x) = 1 \cdot 0.2 + 2 \cdot 0.3 + 3 \cdot 0.5 = 0.2 + 0.6 + 1.5 = 2.3$$
> __Continuous random variable__
> Suppose we have a continuous random variable Y that follows the following equation for the PDF:
> $$g(y) = \begin{cases} 3y^2 \quad \text{for} \quad 0 \geq Y \leq 1 \\ 0 \quad \text{everywhere else} \end{cases}$$
> The expected value of this function is then calculated with:
> $$\begin{align}\mathbb{E}[Y] &= \int^1_0 y \times 3y^2 dy \\&= \left[ \frac{3}{4}y^4 - \frac{3}{4}y^4 \right]^1_0 \\&= \frac{3}{4}1^4 - \frac{3}{4}0^4 \\ &= \frac{3}{4}\end{align}$$

## Variance
The variance is a measure of the spread of a distribution and is defined as follows:
$$
\begin{aligned}
\mathbb{V}[X] & \triangleq \mathbb{E}\left[(X-\mu)^2\right]=\int(x-\mu)^2 p(x) d x \\
& =\int x^2 p(x) d x+\mu^2 \int p(x) d x-2 \mu \int x p(x) d x \\ &=\mathbb{E}\left[X^2\right]-\mu^2
\end{aligned}
$$
__Derivation__:
$$
\begin{aligned}
& \mathbb{V}(x)=\mathbb{E}[x-\mu]^2 \\
& \mathbb{V}(x)=\mathbb{E}\left[x^2-2 x \mu+\mu^2\right] \\
& \mathbb{V}(x)=\mathbb{E}\left[x^2\right]+\mathbb{E}[2] \cdot \mathbb{E}[x] \cdot \mathbb{E}[\mu]+E\left[\mu^2\right] \\
& \mathbb{V}(x)=\mathbb{E}\left[x^2\right]-2 \cdot \mathbb{E}[x] \cdot \mu+\mu^2 \\
& \mathbb{V}(x)=\mathbb{E}\left[x^2\right]-2 \mu^2+\mu^2 \\
& \mathbb{V}(x)=E\left[x^2\right]-\mu^2
\end{aligned}
$$
from this a useful equlibrium can be deduced:
$$\mathbb{E}[X^2] = \sigma^2 + \mu^2$$


## Standard deviation
The standard deviation is defined as the root of the variance: 
$$sd = \sqrt{\mathbb{V}[X]} = \sigma$$
 The standard deviation, is usually more intuitive as its units are the same as those of the variable. 
## Mode 
The mode is defined as the value with the highest probability mass or probability density and is mathematically defined as:
$$x^* = \operatorname*{arg\,max}_x\,p(x)$$



