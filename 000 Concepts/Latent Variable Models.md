---
title: Latent Variable Models
date: 01-06-2023
time: 17:33
author: Luca Trautmann
tags: ["VAE","ML"]
series: "Variational Autoencoder"
chapter: 4
---

# Latent Variable Models
## Learning and Inference in Deep Latent Variable Models
## Latent Variable Models Introduction
- Latent Variable Models take an indirect approach to describing the probability Distribution over a multidimensional random variable $\mathbf{x}$
- The probability distribution of the random variable data is $P(\mathbf{x})$
- LVM try to model this latent variable by modelling a joint distribution $P(\mathbf{x},\mathbf{z})$ of the observed data and a hidden latent variable $\mathbf{z}$. 
- The joint distribution is broken down into its prior and its conditional probability following the laws of joint probabilities and Bayes Rule (__Background__: [[Bayes Theorem]], [[Probability Basics]] [[Interactions between Random Variables]], focus on the <mark style="background: #FFB8EBA6;">product rule</mark>)
$$P(\mathbf{x}) =  P(\mathbf{x}|\mathbf{z})P(\mathbf{z})$$
- To get the probability distribution of $\mathbf{x}$ the joint probability distribution is then marginalised over the latent variable. 
$$
\begin{aligned}
P(\mathbf{x}) &=  \int P(\mathbf{x},\mathbf{z})d\mathbf{z}\\
P(\mathbf{x}) &=  \int P(\mathbf{x}|\mathbf{z})P(\mathbf{z})d\mathbf{z}
\end{aligned}
$$
- here: $P(x|z)$  is the likelihood of the data with respect to the latent variables term and the prior $P(z)$
- <mark style="background: #FFB8EBA6;">The key advantage of this procedure: Both the prior and the likelihood function are relatively easy to model and allow for complex, unknown distributions to be modelled. </mark>

```shell
open -a Visual\ Studio\ Code /Users/luca/Desktop/ML/ScriptsML/notebooks/latent_variable_models.ipynb
```
## Nonlinear Latent Variable Models 
- Conceptually, in non-linear latent variable Models, both $\mathbf{z}$ and $\mathbf{x}$ are continuous and multivariate
- Similarly to more classical machine learning problems, we then use a neural network to parameterise these distributions (see: [[Parameterisating Conditional Distributions with Neural Networks]])
- Usually, the prior is a standard normal with a mean of 0 and the Identity Matrix as the covariance matrix $\mathbf{I}$
$$\begin{aligned}P(\mathbf{z}) &= \mathcal{N}_{\mathbf{z}}[\mathbf{0},\mathbf{I}] \\\\ P(\mathbf{x}|\mathbf{z}) &= \mathcal{N}_{\mathbf{x}} \left[ \mathbf{f[\mathbf{z},\phi], \sigma^2\mathbf{I}} \right] \end{aligned}$$
- Generally the latent variable $\mathbf{z}$ is lower dimensional than the input data $\mathbf{x}$ and the model $\mathbf{f}[\mathbf{z},\phi]$ describes the most important dimensions of the data while all secondary dimension are represented as noise in the variance.
- As before we retain the approximated distribution of the data by marginalising over the latent variable $\mathbf{z}$.
$$
\begin{aligned}
P(\mathbf{x}) &=  \int P(\mathbf{x},\mathbf{z}|\phi)d\mathbf{z}\\\\
P(\mathbf{x}) &=  \int P(\mathbf{x}|\mathbf{z},\phi)P(\mathbf{z})d\mathbf{z} \\\\
P(\mathbf{x}) &= \int \mathcal{N}_{\mathbf{x}} \left[ \mathbf{f[\mathbf{z},\phi], \sigma^2\mathbf{I}} \right] \times \mathcal{N}_{\mathbf{x}} \left[ \mathbf{0,\mathbf{I}} \right] d\mathbf{z}
\end{aligned}
$$
- This can be viewed as an infinite weighted sum (i.e., an infinite mixture) of spherical Gaussians with different means, where the weights are $P(z)$ and the means are the network outputs $\mathbf{f}[\mathbf{x},\phi]$






## Latent Variable Models
- Latent variables are variables that are part of the model but which are not observed and are hence not part of the dataset
- usually denoted with $\mathbf{Z}$
- In case of an unconditional model of observed variable x, the directed graphical model would then represent a joint distribution $p_{\theta}(x, z)$ over both the observed variables $x$ and the latent variables $z$
- The marginal distribution over the observed variables is given by:
$$
p_{\boldsymbol{\theta}}(\mathbf{x})=\int p_{\boldsymbol{\theta}}(\mathbf{x}, \mathbf{z}) d \mathbf{z} \quad \theta\,\text{hereby mean the model parameters and weights}
$$

- This is also called the (single datapoint) <mark style="background: #FFB8EBA6;">marginal likelihood or the model evidence</mark>,\ when taken as a function of $\theta$


## Deep Latent Variable Models






# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```