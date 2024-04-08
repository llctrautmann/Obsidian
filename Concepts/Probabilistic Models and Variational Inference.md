---
title: Probabilistic Models and Variational Inference
date: 23-05-2023
time: 19:40
author: Luca Trautmann
tags: ["VAE","ML"]
series: "Variational Autoencoder"
chapter: 1
---
# Probabilistic Models and Variational Inference
## Conceptual Introduction
- VAEs, are probabilistic generative models; they aim to learn a distribution $P(x)$ over the data
- After training, it is possible to draw (generate) samples from this distribution
- It is common to talk about the VAE as if it is the model of $P(x)$, but this is misleading; the VAE is a neural architecture that is designed to help learn the model for $P(x)$. The final model for $P(x)$ contains neither the “variational” nor the “autoencoder” parts and might be better described as a nonlinear latent variable model.
- Maximum likelihood learning is not straight forward for these kinds of models

## Formal Description
- For all probabilistic models we assume that the observed variable $\mathbf{x}$ is randomly sampled from an unknown underlying process. 
- We also assume that the true probability distribution of this process $P^*(X = x)$ is unknown.
- We then attempt to approximate this underlying process with a model $f[x,\phi]$, with $\phi$ being the model parameters (weights and biases) and $x$ being the inputs
$$\mathbf{x} \sim f[x,\phi]$$
- Learning, is then defined as finding the best model parameters $\hat{\phi}$ so that the model output $f[x,\phi]$ should be as close as possible to the true probability distribution $P^*(X = x)$
$$f[x,\phi] \approx P^*(X = x)$$
- The model $f[x,\phi]$ should be flexible and accurate
- training: [[Parameterisating Conditional Distributions with Neural Networks]]

# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```

