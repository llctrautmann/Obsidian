---
title: Probability Density Function
date:
  - 28-06-2024
time: 11:10
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: $p(y) \triangleq \frac{d}{d y} P(y)$
aliases:
  - PDF
  - pdf
modified: 2024-06-28
---
# Probability Density Function
The PDF of a [[Cumulative distribution function|CDF]] is the derivative function of the [[Cumulative distribution function|cdf]]. 

$$ \large\tag{1}
p(y) \triangleq \frac{d}{d y} P(y)
$$

The pdf of the Gaussian is given by

$$\large\tag{2}
\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}
$$