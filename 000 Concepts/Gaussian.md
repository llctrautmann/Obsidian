---
title: Gaussian
date:
  - 28-06-2024
time: 10:58
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-28
---
# Gaussian / Normal Distributions
## CDF and PDF
The [[Cumulative distribution function|cdf]] of a gaussian normal is given by:

$$\large\tag{1}
\Phi\left(y ; \mu, \sigma^2\right) \triangleq \int_{-\infty}^y \mathcal{N}\left(z \mid \mu, \sigma^2\right) d z
$$


The [[Probability Density Function|pdf]] of the Gaussian is given by: 

$$\large\tag{2}
\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}
$$

[[Probability Density Function|PDF]] and [[Cumulative distribution function|CDF]] describes the relationship and differences between the two 

## The Multivariate Gaussian (normal) Distribution
### Definition
$$ \large\tag{1}
\mathcal{N}(\boldsymbol{y} \mid \boldsymbol{\mu}, \boldsymbol{\Sigma}) \triangleq \frac{1}{(2 \pi)^{D / 2}|\boldsymbol{\Sigma}|^{1 / 2}} \exp \left[-\frac{1}{2}(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu})\right]
$$




# Footnotes

[^1]: Let P(y) be defined as the probability that the random variable Y is less than or equal to y