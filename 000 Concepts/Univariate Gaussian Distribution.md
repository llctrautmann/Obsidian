---
title: Univariate Gaussian Distribution
date:
  - 28-06-2024
time: 10:58
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
🍙: いや
type: 
formula: $\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}$
aliases:
  - normal distribution
  - Normal distribution
modified: 2024-07-23
---
# Univariate Gaussian Distribution
## Introduction
The most widely used distribution of real-valued random variables $y ∈ R$ is the Gaussian distribution, also called the normal distribution.

## Definition
The [[Cumulative distribution function|cdf]] of a gaussian normal is given by:

$$\large\tag{1}
\Phi\left(y ; \mu, \sigma^2\right) \triangleq \int_{-\infty}^y \mathcal{N}\left(z \mid \mu, \sigma^2\right) d z
$$


The [[Probability Density Function|pdf]] of the Gaussian is given by: 

$$\large\tag{2}
\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}
$$

[[Probability Density Function|PDF]] and [[Cumulative distribution function|CDF]] describes the relationship and differences between the two 


## Noteworthy



# Footnotes

[^1]: Let P(y) be defined as the probability that the random variable Y is less than or equal to y