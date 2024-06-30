---
title: Categorical and Multinomial Distributions
date:
  - 30-06-2024
time: 13:28
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: Definition
formula: 
aliases: []
modified: 2024-06-30
---
# Categorical and Multinomial Distributions
## Categorical 
Categorical distributions generalise the [[Bernoulli and Binomial Distribution|bernoulli]] to more than two outcomes $(C>2)$ [^1]. 

The categorical distribution is a discrete probability distribution with one parameter per class:

$$\large\tag{1}
\operatorname{Cat}(y \mid \boldsymbol{\theta}) \triangleq \prod_{c=1}^C \theta_c^{\mathbb{I}(y=c)}
$$

defines the probability mass function of the categorical distribution [^2]. It simplifies to the probability $\theta_y$ of observing the outcome $y$ in the parameter vector $\boldsymbol{\theta}$. This compact form uses the product and indicator function to elegantly represent the selection of the appropriate category's probability.

## Multinomial


## Softmax function





# Footnotes

[^1]: [[murphy2022.pdf#page=83&selection=121,14,127,7&color=yellow|murphy2022, p.53]]
[^2]: The categorical distribution, denoted as $\operatorname{Cat}(y \mid \boldsymbol{\theta})$, describes the probability of observing outcome $y$ given a probability vector $\boldsymbol{\theta} = (\theta_1, \theta_2, \ldots, \theta_C)$, where $\sum_{c=1}^C \theta_c = 1$. It is defined as $\operatorname{Cat}(y \mid \boldsymbol{\theta}) \triangleq \prod_{c=1}^C \theta_c^{\mathbb{I}(y=c)}$, where $\mathbb{I}(y=c)$ is an indicator function that is 1 if $y=c$ and 0 otherwise leading to $\theta=1$. For example, with $\boldsymbol{\theta} = (0.2, 0.5, 0.3)$ for outcomes $A$, $B$, and $C$: $\operatorname{Cat}(A \mid \boldsymbol{\theta}) = 0.2$, $\operatorname{Cat}(B \mid \boldsymbol{\theta}) = 0.5$, and $\operatorname{Cat}(C \mid \boldsymbol{\theta}) = 0.3$, as the formula selects the probability corresponding to the observed outcome $y$ and all other categories default to 1.