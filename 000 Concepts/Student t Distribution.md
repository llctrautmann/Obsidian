---
title: Student t Distribution
date:
  - 01-07-2024
time: 13:59
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-07-01
---
# Student t Distribution
## Introduction
One issue with the gaussian is a sensitivity towards outliers. A robust alternative is the student t distribution. 

## Definition

$$\large\tag{1}
\mathcal{T}\left(y \mid \mu, \sigma^2, \nu\right) \propto\left[1+\frac{1}{\nu}\left(\frac{y-\mu}{\sigma}\right)^2\right]^{-\left(\frac{\nu+1}{2}\right)}
$$

- for lower $\nu$ values the tails are fatter than the gaussian
- $\nu$ is the degrees of freedom
	- with $\nu\gg1$ it rapidly becomes the gaussian 
		- commonly $\nu=4$ as a sensible trade off 
- mean: $\mu$
- mode: $\mu$ 
- variance: $=\frac{\nu \sigma^2}{(\nu-2)}$
