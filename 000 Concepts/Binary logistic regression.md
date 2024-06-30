---
title: Binary logistic regression
date:
  - 19-06-2024
time: 20:59
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
🍙: いや
type: Algorithm
formula: $p(y \mid \boldsymbol{x} ; \boldsymbol{\theta})=\operatorname{Ber}\left(y \mid \sigma\left(\boldsymbol{w}^{\top} \boldsymbol{x}+b\right)\right)$
aliases:
  - BLG
modified: 2024-06-19
---
# Binary logistic regression
- The basic formula of BLG is[^1]: 
$$\large\tag{1}
p(y \mid \boldsymbol{x} ; \boldsymbol{\theta})=\operatorname{Ber}\left(y \mid \sigma\left(\boldsymbol{w}^{\top} \boldsymbol{x}+b\right)\right)
$$
- it is some linear combination of features and bias mapped into $[0,1]$-Range by the [[sigmoid function]] and the result is used as the estimated underlying probability parameter. 

# Footnotes
[^1]: [[murphy2022.pdf#page=82&selection=345,0,363,1&color=yellow|murphy2022, p.52]]