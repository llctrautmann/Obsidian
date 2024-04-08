---
title: Diffusion Models
date: 18-12-2023
time: 11:54
output: meansquarederror.xyz
author: Luca Trautmann
tags:
---

# Diffusion Models

A notable property of the forward process is that it admits sampling $\mathbf{x}_t$ at an arbitrary timestep $t$ in closed form: using the notation $a_t := 1 - \beta_t$ and $\bar{a}_t := \prod^t_{s=1}\alpha_s$ we reach: 
$$
 q\left(\mathbf{x}_t \mid \mathbf{x}_0\right)=\mathcal{N}\left(\mathbf{x}_t ; \sqrt{\bar{\alpha}_t \mathbf{x}_0},\left(1-\bar{\alpha}_t\right) \mathbf{I}\right).
$$

> $x_t$ is distributed according to a Gaussian distribution with a mean of $\sqrt{(alpha_t * x_0)}$ and a covariance matrix of $(1 - alpha_t) * I$ 

Sampling from this distribution is now the same as the reparameterisation trick in a VAE. This leads to the following expression:

$$
\text{mean} + \text{std} + \epsilon \quad \epsilon \sim \mathcal{N}(0,1)
$$

or in the context of the diffusion model: 

$$
\sqrt{\bar{\alpha}_t \mathbf{x}_0} + \sqrt{\left(1-\bar{\alpha}_t\right) \mathbf{I}} + \epsilon
$$

The final loss function for the diffusion model is at last: 
$$
=\mathbb{E}_{\mathbf{x}_0, \boldsymbol{\epsilon}}\left[\frac{1}{2 \sigma_t^2}\left\|\frac{1}{\sqrt{\alpha_t}}\left(\mathbf{x}_t\left(\mathbf{x}_0, \boldsymbol{\epsilon}\right)-\frac{\beta_t}{\sqrt{1-\bar{\alpha}_t}} \boldsymbol{\epsilon}\right)-\boldsymbol{\mu}_\theta\left(\mathbf{x}_t\left(\mathbf{x}_0, \boldsymbol{\epsilon}\right), t\right)\right\|^2\right]
$$
It is possible to either predict the noise or the mean of the distribution, with the noise receiving preferential treatment. The simplified loss function for the diffusion process can then be written as: 
$$
L_{\text {simple }}(\theta):=\mathbb{E}_{t, \mathbf{x}_0, \boldsymbol{\epsilon}}\left[\left\|\boldsymbol{\epsilon}-\boldsymbol{\epsilon}_\theta\left(\sqrt{\bar{\alpha}_t} \mathbf{x}_0+\sqrt{1-\bar{\alpha}_t} \boldsymbol{\epsilon}, t\right)\right\|^2\right]
$$
