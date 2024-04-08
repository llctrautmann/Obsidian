---
title: ELBO - Evidence Lower Bound
date: 31-05-2023
time: 09:24
author: Luca Trautmann
tags: ["ML"]
series: "Variational Autoencoder"
chapter: 6
---

# ELBO - Evidence Lower Bound
## ELBO - Introduction
The evidence lower bound (ELBO) is a central concept in the context of variational autoencoders (VAEs). VAEs are a type of deep learning model that can be used for generative tasks such as image and text generation. They consist of two main components: an encoder and a decoder. The encoder maps the input data to a latent space, while the decoder maps the latent space back to the original data space. The goal of a VAE is to learn a distribution over the latent space that captures the underlying structure of the data.

The ELBO is a measure of the quality of the learned distribution over the latent space. It is defined as the difference between the marginal likelihood of the data and the Kullback-Leibler (KL) divergence between the learned distribution and a prior distribution over the latent space. The marginal likelihood of the data is the probability of the data given the parameters of the model. The KL divergence measures the distance between the learned distribution and the prior distribution. The ELBO can be written as:

$$ELBO = E[\log p(x|z)] - KL(q(z|x) || p(z))$$

where x is the input data, z is the latent variable, p(x|z) is the likelihood of the data given the latent variable, q(z|x) is the posterior distribution over the latent variable given the data, and p(z) is the prior distribution over the latent variable.

The ELBO is an important quantity in VAEs because it provides a lower bound on the marginal likelihood of the data. This means that maximising the ELBO is equivalent to maximising the marginal likelihood of the data. However, maximising the ELBO also has the additional benefit of encouraging the learned distribution to be close to the prior distribution over the latent space. This is because the KL divergence term penalises distributions that are far from the prior distribution.

The ELBO can be optimised using stochastic gradient descent (SGD) or a related optimisation algorithm. During training, the model is presented with a batch of data samples and the gradients of the ELBO with respect to the model parameters are computed. These gradients are then used to update the model parameters in the direction that maximizes the ELBO.

One important consideration when using the ELBO in VAEs is the trade-off between the reconstruction error and the KL divergence term. The reconstruction error term encourages the model to reconstruct the input data accurately, while the KL divergence term encourages the learned distribution to be close to the prior distribution. If the reconstruction error term is given too much emphasis, the learned distribution may not capture the true underlying structure of the data. On the other hand, if the KL divergence term is given too much emphasis, the model may produce overly blurry or uninformative samples.

In summary, the evidence lower bound is a measure of the quality of the learned distribution over the latent space in variational autoencoders. It provides a lower bound on the marginal likelihood of the data and encourages the learned distribution to be close to a prior distribution over the latent space. Maximising the ELBO is an important step in training VAEs and requires careful consideration of the trade-off between the reconstruction error and the KL divergence term.

## Reasoning
- From the note on [[Latent Variable Models]], it becomes apparent, that in the VAE framework the goal is to approximate the distribution of the input data $\mathbf{x}$ ($P(\mathbf{x})$)with <mark style="background: #FFB86CA6;">the integral</mark> of two other distributions (the prior $P(\mathbf{z})$ and the likelihood $P(\mathbf{x} | \mathbf{z})$ following the product rule ([[Interactions between Random Variables]]) stating any joint probability can be broken down into likelihood and prior (Marginalisation). 
$$P(\mathbf{x}) =  \int P(\mathbf{x}|\mathbf{z})P(\mathbf{z})d\mathbf{z}$$
- In the training process we want to find the new parameters $\hat{\phi}$, that maximise the log-likelihood over the dataset $\mathbf{x}_i$ 
$$
\hat{\boldsymbol{\phi}}=\underset{\phi}{\operatorname{argmax}}\left[\sum_{i=1}^I \log \left[\operatorname{Pr}\left(\mathbf{x}_i \mid \phi\right)\right]\right],
$$
where:

$$
\operatorname{Pr}\left(\mathbf{x}_i \mid \phi\right)=\int \operatorname{Norm}_{\mathbf{x}_i}\left[\mathbf{f}[\mathbf{z}, \phi], \sigma^2 \mathbf{I}\right] \cdot \operatorname{Norm}_{\mathbf{z}}[\mathbf{0}, \mathbf{I}] d \mathbf{z}
$$

- This integral is unfortunately intractable and hence cannot be solved analytically. Therefore the probability distribution needs to be approximated with the Evidence Lower Bound (ELBO)

# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
