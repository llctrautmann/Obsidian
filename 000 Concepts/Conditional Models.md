---
title: Conditional Models
date: 01-06-2023
time: 15:12
author: Luca Trautmann
tags: ['ML','VAE']
series: "Variational Autoencoder"
chapter: 2
---

# Conditional Models
- as mentioned in the machine learning fundamental series (see [[Parameterisating Conditional Distributions with Neural Networks]]), we usually want to learn a conditional model instead of an unconditional model.
- Hence we want to learn, the probability of the output given the input:
$$p(y|x)$$
- A good model prediction will then follow the same logic and can be written as:
$$f[x,\phi] \approx p^*(y|x)$$
- To do so we define a probability distribution and predict one of the parameters of the probability distribution
$$
\begin{aligned}
\mathbf{p} & =\operatorname{NeuralNet}(\mathbf{x}) \\
p_{\boldsymbol{\theta}}(y \mid \mathbf{x}) & =\operatorname{Categorical}(y ; \mathbf{p})
\end{aligned}
$$
- The training of a fully observed model is conducted in the same way as described in [[Parameterisating Conditional Distributions with Neural Networks]]


# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1) OR (series = ["Variational Autoencoder","Machine Learning Fundamentals"] AND chapter = this.chapter + 1) OR (series = ["Variational Autoencoder","Machine Learning Fundamentals"] AND chapter = this.chapter - 1)
SORT chapter asc
```

