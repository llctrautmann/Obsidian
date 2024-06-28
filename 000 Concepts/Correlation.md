---
title: Correlation
date:
  - 28-06-2024
time: 16:31
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-28
---
# Correlation
[[Covariance]] are not range-bound. Correlations are normalised covariances and are bound between -1 and 1. 

$$ \large\tag{1} 
\rho \triangleq \operatorname{corr}[X, Y] \triangleq \frac{\operatorname{Cov}[X, Y]}{\sqrt{\mathbb{W}[X] V[Y]}}
$$

## Noteworthy
- A better way of thinking about correlation is: _degree of linearity_ [^1] 
	- More informative are measures of mutual information like the [[Kullback-Leibler (KL) divergence]] [^2]. 
- 
# Footnotes

[^1]: [[murphy2022.pdf#page=108&selection=181,86,185,1&color=yellow|murphy2022, p.78]]
[^2]: [[murphy2022.pdf#page=109&selection=192,42,193,69&color=yellow|murphy2022, p.79]]