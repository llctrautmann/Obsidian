---
title: Variational Inference
date: 18-05-2023
time: 15:06
author: Luca Trautmann
tags: ["ML", "Mathematics"]
series: Machine Learning Fundamentals
chapter: 2
---

> [!Series]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Variational Inference

- Estimation Method for the posterior distribution $P(z|D)$ where $z$ are latent variables and $D$ is the observed data.  
- In Reality we are looking at Direct Graphical Models with observed variables $\vec{X}_{\mathbb{R}^N}$ and latent variables $\vec{z}_{\mathbb{R}^D}$ 
- An example for latent variable and data X, would be the images for X (very high dimension) and the latent variables could be the camera angle (related to [[Manifold Hypothesis]])
- The task is always to do inference to get the posterior; in this case the posterior is $p(\vec{z} | X = D)$, which out loud translates to the probability distribution of the latent variable given the (fixed) data
- We have access to the joint probability $P(X,z)$ 
- in [[Bayes Theorem]]: $P(\vec{z}|\vec{X} = D) = \frac{P(Z)\times P(\vec{X} = D|\vec{z})}{P(\vec{X}=D)}$ , the denominator is intractable because we cannot solve the necessary integral (another way to approximate solutions is [[Markov Chain Monte Carlo]] Sampling with the Metropolis Hasting Algorithm.
- $P(Z)$ will usually be assumed to follow an easily calculable distribution (i.e. a normal Gaussian Distribution)


