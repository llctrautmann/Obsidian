---
title: Multivariate Gaussian Distribution
date:
  - 23-07-2024
time: 09:55
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: $\mathcal{N}(\boldsymbol{y} \mid \boldsymbol{\mu}, \boldsymbol{\Sigma}) \triangleq \frac{1}{(2 \pi)^{D / 2}|\boldsymbol{\Sigma}|^{1 / 2}} \exp \left[-\frac{1}{2}(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu})\right]$
aliases: 
modified: 2024-07-23
Docstring:
  - The multivariate Gaussian is the most commonly used distribution for continuous random variables.
---
# Multivariate Gaussian Distribution
## Introduction
- Most commonly used for continuous random variables.
	- Reasonable assumptions in most cases

## Definition
The Multivariate Gaussian (normal) Distribution is given by: 

$$ \large\tag{1}
\mathcal{N}(\boldsymbol{y} \mid \boldsymbol{\mu}, \boldsymbol{\Sigma}) \triangleq \frac{1}{(2 \pi)^{D / 2}|\boldsymbol{\Sigma}|^{1 / 2}} \exp \left[-\frac{1}{2}(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu})\right]
$$


where $\boldsymbol{\mu}=\mathbb{E}[\boldsymbol{y}] \in \mathbb{R}^D$ is the mean vector, and $\boldsymbol{\Sigma}=\operatorname{Cov}[\boldsymbol{y}]$ is the $D \times D$ covariance matrix, defined as follows:

$$\large
\begin{aligned}
\operatorname{Cov}[\boldsymbol{y}] & \triangleq \mathbb{E}\left[(\boldsymbol{y}-\mathbb{E}[\boldsymbol{y}])(\boldsymbol{y}-\mathbb{E}[\boldsymbol{y}])^{\top}\right] \\
& =\left(\begin{array}{cccc}
\mathbb{V}\left[Y_1\right] & \operatorname{Cov}\left[Y_1, Y_2\right] & \cdots & \operatorname{Cov}\left[Y_1, Y_D\right] \\
\operatorname{Cov}\left[Y_2, Y_1\right] & \mathbb{V}\left[Y_2\right] & \cdots & \operatorname{Cov}\left[Y_2, Y_D\right] \\
\vdots & \vdots & \ddots & \vdots \\
\operatorname{Cov}\left[Y_D, Y_1\right] & \operatorname{Cov}\left[Y_D, Y_2\right] & \cdots & \mathbb{V}\left[Y_D\right]
\end{array}\right)
\end{aligned}
$$

where:

$$\large
\operatorname{Cov}\left[Y_i, Y_j\right] \triangleq \mathbb{E}\left[\left(Y_i-\mathbb{E}\left[Y_i\right]\right)\left(Y_j-\mathbb{E}\left[Y_j\right]\right)\right]=\mathbb{E}\left[Y_i Y_j\right]-\mathbb{E}\left[Y_i\right] \mathbb{E}\left[Y_j\right]
$$

and $\mathbb{V}\left[Y_i\right]=\operatorname{Cov}\left[Y_i, Y_i\right]$. From Equation (3.12), we get the important result

$$\large
\mathbb{E}\left[\boldsymbol{y} \boldsymbol{y}^{\top}\right]=\boldsymbol{\Sigma}+\boldsymbol{\mu} \boldsymbol{\mu}^{\top}
$$
## Noteworthy

