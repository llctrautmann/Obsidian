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

Given a pdf, we can compute the probability of a continuous variable being in a finite interval as follows:
$$ \large\tag{2}
\operatorname{Pr}(a<Y \leq b)=\int_a^b p(y) d y=P(b)-P(a)
$$

The pdf of the Gaussian is given by

$$\large\tag{3}
\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}
$$

## Noteworthy
- A function $f: \mathbb{R}^D \rightarrow \mathbb{R}$ is called a probability density function (PDF) if
	1. $\forall x \in \mathbb{R}^D: f(x) \geqslant 0$
	2. Its integral exists and $\int_{\mathbb{R}^D} f(\boldsymbol{x}) \mathrm{d} \boldsymbol{x}=1$
