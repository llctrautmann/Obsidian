---
title: Maximum Likelihood Estimation (MLE)
date:
  - 23-07-2024
time: 10:46
author: Luca Trautmann
tags:
  - Statistics
series: Statistics
🍙: いや
type: Concept
Docstring: 
formula: 
aliases: 
modified: 2024-07-23
---
# Maximum Likelihood Estimation (MLE)
## Introduction
- The basics premise behind maximum likelihood estimation is to assign those parameters that result in the highest probability for the training data [^2]. 


## Formal Definitions

$$\large\tag{1}\hat{\boldsymbol{\theta}}_{\text {mle }} \triangleq \underset{\boldsymbol{\theta}}{\operatorname{argmax}} p(\mathcal{D} \mid \boldsymbol{\theta})$$
- The most common assumption is that the training samples are i.i.d. 
	- The iid assumptions makes the math easier, as we can use the multiplication rule from probability theory to construct the joint probability

$$\large\tag{2}p(\mathcal{D} \mid \boldsymbol{\theta})=\prod_{n=1}^N p\left(\boldsymbol{y}_n \mid \boldsymbol{x}_n, \boldsymbol{\theta}\right)$$
- numerical stability in computers requires some transformation with a monotonically increasing function. In almost all cases we use the `log` to obtain the log-likelihood
$$\large\tag{3}\ell(\boldsymbol{\theta}) \triangleq \log p(\mathcal{D} \mid \boldsymbol{\theta})=\sum_{n=1}^N \log p\left(\boldsymbol{y}_n \mid \boldsymbol{x}_n, \boldsymbol{\theta}\right)$$



## Noteworthy


# Footnotes
[^2]: [[murphy2022.pdf#page=137&selection=78,0,79,33&color=yellow|murphy2022, p.107]]