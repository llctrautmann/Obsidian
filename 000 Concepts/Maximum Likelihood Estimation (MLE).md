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
formula: $\nabla_{\boldsymbol{\theta}} \operatorname{NLL}(\boldsymbol{\theta})=\mathbf{0}$
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
- to obtain the best estimate over the entire data stack we then just use the `argmax` of the joint probability distribution

$$\large\tag{4}\hat{\boldsymbol{\theta}}_{\mathrm{mle}}=\underset{\boldsymbol{\theta}}{\operatorname{argmax}} \sum_{n=1}^N \log p\left(\boldsymbol{y}_n \mid \boldsymbol{x}_n, \boldsymbol{\theta}\right)$$

- ML notation usually assumes a minimisation task so the NNL is just the negative log-likelihood

$$\large\tag{5}
\mathrm{NLL}(\boldsymbol{\theta}) \triangleq-\log p(\mathcal{D} \mid \boldsymbol{\theta})=-\sum_{n=1}^N \log p\left(\boldsymbol{y}_n \mid \boldsymbol{x}_n, \boldsymbol{\theta}\right)
$$

- Minimising this will give the MLE. If the model is unconditional (unsupervised), the MLE becomes
$$\large\tag{6}
\hat{\boldsymbol{\theta}}_{\mathrm{mle}}=\underset{\boldsymbol{\theta}}{\operatorname{argmin}}-\sum_{n=1}^N \log p\left(\boldsymbol{y}_n \mid \boldsymbol{\theta}\right)
$$

## Noteworthy
- One important justification of the MLE is that the model distribution is a close as possible to the data distribution [^3]

# Footnotes
[^2]: [[murphy2022.pdf#page=137&selection=78,0,79,33&color=yellow|murphy2022, p.107]]
[^3]: [[murphy2022.pdf#page=139&selection=84,0,100,12&color=yellow|murphy2022, p.109]]