---
title: ELBO - Derivation
date: 11-06-2023
time: 13:30
author: Luca Trautmann
tags: ["ML","VAE"]
series: "Variational Autoencoder"
chapter:  7
---


# ELBO - Derivation
To derive the [[ELBO - Evidence Lower Bound]] (ELBO) we start with [[Latent Variable Models]]. Latent variable models take an indirect approach to describing a complex probability distribution $P(x)$ over a multidimensional variable $x$. The approach models $P(x)$ with a joint probability distribution $P(x,z)$ over $x$ and a hidden latent variable $z$. The probability distribution $P(x,z)$ is then marginalised w.r.t. $z$ to obtain $P(x)$.
$$\operatorname{Pr}(\mathbf{x})=\int \operatorname{Pr}(\mathbf{x}, \mathbf{z}) d \mathbf{z}$$
This term is relatively useless and has to be broken down using the product rule of probabilities ([[Interactions between Random Variables]]).

$$\operatorname{Pr}(\mathbf{x})=\int \operatorname{Pr}(\mathbf{x} \mid \mathbf{z}) \operatorname{Pr}(\mathbf{z}) d \mathbf{z}$$
In principle this is a good procedure, because it allows us to describe complex probability distributions with simple components. 

>[! Example: Mixture of Gaussians]
>Example: mixture of Gaussians
In a $1 \mathrm{D}$ mixture of Gaussians (figure 17.1a), the latent variable $z$ is discrete, and the prior $\operatorname{Pr}(z)$ is a categorical distribution (figure 5.9) with one probability $\lambda_n$ for each possible value of $z$. The likelihood $\operatorname{Pr}(x \mid z=n)$ of the data $x$ given that the latent variable $z$ takes value $n$ is normally distributed with mean $\mu_n$ and variance $\sigma_n^2$ :
> $$\begin{aligned}\operatorname{Pr}(z=n) & =\lambda_n\\\operatorname{Pr}(x \mid z=n) & =\operatorname{Norm}_x\left[\mu_n, \sigma_n^2\right]\end{aligned}$$
> As in equation 17.2 , the likelihood $\operatorname{Pr}(x)$ is given by the marginalization over the latent variable $z$ (figure $17.1 \mathrm{~b}$ ). Here, the latent variable is discrete, so we sum over its possible values to marginalize:
> $$\begin{aligned}\operatorname{Pr}(x) & =\sum_{n=1}^N\operatorname{Pr}(x, z=n) \\& =\sum_{n=1}^N \operatorname{Pr}(x \mid z=n) \cdot \operatorname{Pr}(z=n) \\& =\sum_{n=1}^N \lambda_n \cdot \operatorname{Norm}_x\left[\mu_n, \sigma_n^2\right]\end{aligned}$$
> From simple expressions for the likelihood and prior, we describe a complex multi-modal probability distribution.
> Hold ⌘ for visual example: [[Mixture_of_Gaussians.png]]

In contrast to the simple example above, the integral for $P(x,z)$ is intractable for more complex multivariate and continuous data and latent variables. 
## Training for LVM 
Like in all models (see: [[Parameterisating Conditional Distributions with Neural Networks]]) we want to maximise the log-likelihood over a training dataset: 

$$
\hat{\boldsymbol{\phi}}=\underset{\phi}{\operatorname{argmax}}\left[\sum_{i=1}^I \log \left[\operatorname{Pr}\left(\mathbf{x}_i \mid \phi\right)\right]\right]
$$
where:
$$
\operatorname{Pr}\left(\mathbf{x}_i \mid \phi\right)=\int \operatorname{Norm}_{\mathbf{x}_i}\left[\mathbf{f}[\mathbf{z}, \phi], \sigma^2 \mathbf{I}\right] \cdot \operatorname{Norm}_{\mathbf{z}}[\mathbf{0}, \mathbf{I}] d \mathbf{z}
$$
Hence:
$$\hat{\boldsymbol{\phi}}=\underset{\phi}{\operatorname{argmax}}\left[\sum_{i=1}^I \log \left[\int \operatorname{Norm}_{\mathbf{x}_i}\left[\mathbf{f}[\mathbf{z}, \phi], \sigma^2 \mathbf{I}\right] \cdot \operatorname{Norm}_{\mathbf{z}}[\mathbf{0}, \mathbf{I}] d \mathbf{z}\right]\right]$$
where our neural network predicts the $\mu$ of the the likelihood function. However, as eluded before, this is intractable and hence we need to find an appropriate approximation. This approximation is the ELBO - Evidence Lower Bound. 

## Deriving the ELBO from Jensen's Inequality
Jensen's inequality states, that for a concave function (see [[Convexity in Mathematical Functions]]), of the expectation of data $x$ is greater than or equal to the expectation of the function of the data:
$$
g[\mathbb{E}[x]] \geq \mathbb{E}[g[x]]
$$
In this case, the concave function is the logarithm, so we have:
$$
\log [\mathbb{E}[y]] \geq \mathbb{E}[\log [y]]
$$
or writing out the expression for the expectation in full, we have:
$$
\log \left[\int \operatorname{Pr}(y) y d y\right] \geq \int \operatorname{Pr}(y) \log [y] d y
$$
(see script __jensens_inequality.ipynb__) 

## Deriving the ELBO in Detail
There are multiple equivalent forms of the ELBO that can be derived with the Jensen's Inequality. We start initially with the log-likelihood of the distribution we want to approximate with the ELBO. In the case here, it is the data distribution $P(x) = \int P(x,z)dz = \int P(z) \times P(x|z)dz$ is the expected value of the data likelihood. (see: [[Expected Values and Latent Variable Models]]). 

To derive the ELBO from first principles we start with the log-likelihood.  We multiply the original log-likelihood with an arbitrary PDF $q(x)$ resulting in the following expression:
$$
\begin{aligned}
\log [\operatorname{Pr}(\mathbf{x} \mid \phi)] & =\log \left[\int \operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \phi) d \mathbf{z}\right] \\
& =\log \left[\int q(\mathbf{z}) \frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \boldsymbol{\phi})}{q(\mathbf{z})} d \mathbf{z}\right]
\end{aligned}
$$
In the context of the ELBO, we can then write the Jensen's Inequality as follows:

$$
\log \left[\int q(\mathbf{z}) \frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \phi)}{q(\mathbf{z})} d \mathbf{z}\right] \geq \int q(\mathbf{z}) \log \left[\frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \phi)}{q(\mathbf{z})}\right] d \mathbf{z},
$$

The right side is the Evidence Lower Bound (ELBO). Usually, the arbitrary PDF is also parameterised with a neural network and has the parameters $\theta$. Hence the expression for the ELBO is: 
$$
\operatorname{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}]=\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z}
$$

In principle the ELBO is the loss function of the VAE (see: [[Parameterisating Conditional Distributions with Neural Networks]])

## ELBO Properties
- The ELBO is a lower bound on the log-likelihood of the data in Bayesian inference.
- The original log-likelihood is a function of the parameters, and the goal is to find its maximum.
- The ELBO is also a function of the parameters, but it must always be below the original likelihood function.
- By changing the parameters $\theta$, the lower bound function can be modified, and by changing the value of the $\phi$ parameters, one can move along the lower bound function.
- The ELBO is used in variational inference to approximate complex posterior distributions by finding a simpler distribution that is close to the true posterior.

## Tightness of Bound
The ELBO is tight when, for a fixed value of $\phi$, the ELBO and the likelihood function coincide. To find the distribution $q(\mathbf{z} \mid \boldsymbol{\theta})$ that makes the bound tight, we factor the numerator of the log term in the ELBO using the definition of conditional probability:

$$
\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z}
$$

Using the product rule of probabilities we <mark style="background: #FFB8EBA6;">expand</mark> the term: 

$$\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\phi}) \operatorname{Pr}(\mathbf{x} \mid \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z}
$$

and with the<mark style="background: #FFB8EBA6;"> log rule</mark> ( $\log(\frac{ab}{c}) = \log{a} + \log{b} - \log{c}$ ) we get the following expressions:

$$\begin{aligned}
\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] &= \int q(\mathbf{z} \mid \boldsymbol{\theta}) \biggl(\log[\operatorname{Pr}(\mathbf{x} \mid \boldsymbol{\phi})] +  \log[\operatorname{Pr}(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\phi})] - \log[\operatorname{Pr}(\mathbf{z} \mid \boldsymbol{\theta})] \biggr)
\\&=\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log [\operatorname{Pr}(\mathbf{x} \mid \boldsymbol{\phi})] d \mathbf{z}+\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z}
\end{aligned}$$

The first integral collapses to 1 and the second and third log can be written as a fraction:
$$
\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] =\log [\operatorname{Pr}(\mathbf{x} \mid \boldsymbol{\phi})]+\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z} \quad \text{| Integral of PDF = 1}
$$

This then leads to the final form of the ELBO, which is the original log-likelihood minus the KL Divergence (see [[Kullback-Leibler (KL) divergence]]).
$$
\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] =\log [\operatorname{Pr}(\mathbf{x} \mid \boldsymbol{\phi})]-\mathrm{D}_{K L}[q(\mathbf{z} \mid \boldsymbol{\theta}) \| \operatorname{Pr}(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\phi})]
$$
From this follows that, the KL distance will be zero, and the bound will be tight when $q(z|\theta) = P(z|x, \phi)$. So the approximated arbitrary posterior distribution $q(\mathbf{z} \mid \boldsymbol{\theta})$ will be similar to the posterior distribution of the latent variable.  


## ELBO as reconstruction loss minus KL distance to prior
Depending on the breakdown of the logarithm in the original version of the ELBO, an equivalent form can be generated. 
$$
\begin{aligned}
\mathrm{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}] & =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{x}, \mathbf{z} \mid \boldsymbol{\phi})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z} \\
& =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{x} \mid \mathbf{z}, \boldsymbol{\phi}) \operatorname{Pr}(\mathbf{z})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z} \\
& =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log [\operatorname{Pr}(\mathbf{x} \mid \mathbf{z}, \boldsymbol{\phi})] d \mathbf{z}+\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log \left[\frac{\operatorname{Pr}(\mathbf{z})}{q(\mathbf{z} \mid \boldsymbol{\theta})}\right] d \mathbf{z} \\
& =\int q(\mathbf{z} \mid \boldsymbol{\theta}) \log [\operatorname{Pr}(\mathbf{x} \mid \mathbf{z}, \boldsymbol{\phi})] d \mathbf{z}-\mathrm{D}_{K L}[q(\mathbf{z} \mid \boldsymbol{\theta}) \| \operatorname{Pr}(\mathbf{z})],
\end{aligned}
$$
In this formulation, the first term measures the average agreement P r(x|z, ϕ) of the latent variable and the data. This is termed the reconstruction loss. The second term measures the degree to which the auxiliary distribution q(z|θ) matches the prior. <mark style="background: #FFB86CA6;">This formulation is the one that is used in the variational autoencoder. </mark>

In a real world code example the loss function for a VAE with the [[Reparameterisation Trick]] looks like this:
```python
for epoch in range(epochs):
	model.train()
	for idx, batch in enumerate(train_loader):

		batch = batch.to(device)
		reconstruction, mu, log_var = model(batch)

		# Reconstruction loss		
		reconstruction_loss = criterion(reconstruction, batch)`
		
		# KL Divergence
		kl_divergence = -0.5 * torch.sum(1 + log_var - mu.pow(2) - log_var.exp())
		
		# Total loss
		total_loss = reconstruction_loss + beta * kl_divergence
		
		# Backprop		
		optimizer.zero_grad()
		total_loss.backward()
		optimizer.step()
```

# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
