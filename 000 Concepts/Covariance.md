---
title: Covariance
date:
  - 28-06-2024
time: 16:31
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-28
---
# Covariance

The covariance is a measure of the linear relationship between two [[Random Variables|RVs]] [^1]. 

$$ \large\tag{1}
\operatorname{Cov}[X, Y] \triangleq \mathbb{E}[(X-\mathbb{E}[X])(Y-\mathbb{E}[Y])]=\mathbb{E}[X Y]-\mathbb{E}[X] \mathbb{E}[Y]
$$

If $x$ is a $D$-dimensional random vector, its covariance matrix is defined to be the following symmetric, positive semi definite matrix:
$$
\begin{aligned}
\operatorname{Cov}[x] & \triangleq \mathbb{E}\left[(x-\mathbb{E}[x])(x-\mathbb{E}[x])^{\top}\right] \triangleq \boldsymbol{\Sigma} \\
& =\left(\begin{array}{cccc}
\mathbb{V}\left[X_1\right] & \operatorname{Cov}\left[X_1, X_2\right] & \cdots & \operatorname{Cov}\left[X_1, X_D\right] \\
\operatorname{Cov}\left[X_2, X_1\right] & \mathbb{V}\left[X_2\right] & \cdots & \operatorname{Cov}\left[X_2, X_D\right] \\
\vdots & \vdots & \ddots & \vdots \\
\operatorname{Cov}\left[X_D, X_1\right] & \operatorname{Cov}\left[X_D, X_2\right] & \cdots & \mathbb{V}\left[X_D\right]
\end{array}\right)
\end{aligned}
$$
# Footnotes

[^1]: [[murphy2022.pdf#page=107&selection=15,0,39,9&color=yellow|murphy2022, p.77]]