---
title: Optimisation
date:
  - 26-07-2024
time: 18:03
author: Luca Trautmann
tags:
  - None
series: Machine Learning
🍙: いや
type: Concept
formula: 
aliases: 
modified: 2024-07-26
---
# Optimisation
## Introduction
- The basic issue in ML is always parameter estimation
- We solve a scalar-valued cost function as a minimisation problem [^1]. 

$$\large\tag{1}
\boldsymbol{\theta}^* \in \underset{\boldsymbol{\theta} \in \Theta}{\operatorname{argmin}} \mathcal{L}(\boldsymbol{\theta})
$$

- The basic assumption is that $\Theta \subseteq\mathbb{R}^D$
	- parameters are real-valued 
	- leading to continuous optimisation

## Local vs. Global
- A point that solves (1) is a global optimum [^2].
	- in most cases there is no analytical solution / its intractable
- most solver search for any form of optimum (local)
- if $\exists \delta>0, \forall \boldsymbol{\theta} \in \Theta, \boldsymbol{\theta} \neq \boldsymbol{\theta}^*:\left\|\boldsymbol{\theta}-\boldsymbol{\theta}^*\right\|<\delta, \mathcal{L}\left(\boldsymbol{\theta}^*\right)<\mathcal{L}(\boldsymbol{\theta})$ holds the algorithm has found a local 
# Footnotes

[^1]: [[murphy2022.pdf#page=303&selection=15,2,38,0&color=yellow|murphy2022, p.273]]
[^2]: [[murphy2022.pdf#page=303&selection=130,0,133,1&color=yellow|murphy2022, p.273]]