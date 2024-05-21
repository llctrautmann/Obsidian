---
title: High-Dimensional Variance
date:
  - 02-04-2024
time: 11:09
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 5
status: Incomplete
modified: 2024-05-03
---
# High-Dimensional Variance

For a random variable $X$, the variance is defined as the mean squared difference from the mean:

$$\mathbb{V}[X]:=\sigma^2=\mathbb{E}\left[(X-\mathbb{E}[X])^2\right]$$

The mean or EV is the central tendency of the RV [[Random Variables]], while the variance shows me the spread of the RV around its mean. This is easy and manageable for a single RV.

## The Covariance Matrix
What happens if I see a vector of Random Variables? 

$$
\mathbf{X}=\left[\begin{array}{c}X_1 \\ X_2 \\ \vdots \\ X_n\end{array}\right]
$$

In this case the standard notation is the covariance matrix: 

$$
\operatorname{cov}[\mathbf{X}]:=\boldsymbol{\Sigma}=\mathbb{E}\left[(\mathbf{X}-\mathbb{E}[\mathbf{X}])(\mathbf{X}-\mathbb{E}[\mathbf{X}])^{\top}\right]
$$

I should think about the covariance as the a high-dimensional variance. 

## Definition
It is clear to me that the covariance is related to the variance. The equations are pretty similar. 

$$\boldsymbol{\Sigma}=\left[\begin{array}{ccc}\mathbb{E}\left[\left(X_1-\mathbb{E}\left[X_1\right]\right)\left(X_1-\mathbb{E}\left[X_1\right]\right)\right] & \ldots & \mathbb{E}\left[\left(X_1-\mathbb{E}\left[X_1\right]\right)\left(X_n-\mathbb{E}\left[X_n\right]\right)\right] \\ \vdots & \ddots & \vdots \\ \mathbb{E}\left[\left(X_n-\mathbb{E}\left[X_n\right]\right)\left(X_1-\mathbb{E}\left[X_1\right]\right)\right] & \ldots & \mathbb{E}\left[\left(X_n-\mathbb{E}\left[X_n\right]\right)\left(X_n-\mathbb{E}\left[X_n\right]\right)\right]\end{array}\right]$$

On the diagonal we have the variances of the RV and on the off-diagonals we have the covariances between random variables. This is very useful has has been used in [[@feiner2023]].

The covariances

$$
\sigma_{i j}:=\operatorname{cov}\left(X_i, X_j\right)=\mathbb{E}\left[\left(X_i-\mathbb{E}\left[X_i\right]\right)\left(X_j-\mathbb{E}\left[X_j\right]\right)\right]
$$

shows that the variance of a single RV is just a special case of the more general covariance definition of two random variables.

$$
\mathbb{V}\left[X_i\right]=\operatorname{cov}\left(X_i, X_i\right)
$$
## Pearson's Correlation
Regardless of the variance of the underlying random variables, the correlation direction will stay the same. This shows me that there is also information about the correlation contained in the covariance matrix. 

$$
\sigma_{i j}=\rho_{i j} \sigma_i \sigma_j
$$
`Note: for a univariate covariance pearson's coefficient is 1 and we get the equation above.`

This gives me this picture of the covariance matrix:

$$
\boldsymbol{\Sigma}=\left[\begin{array}{cccc}
\sigma_1^2 & \rho_{12} \sigma_1 \sigma_2 & \ldots & \rho_{1 n} \sigma_1 \sigma_n \\
\rho_{21} \sigma_2 \sigma_1 & \sigma_2^2 & \ldots & \rho_{2 n} \sigma_2 \sigma_n \\
\vdots & \ddots & \vdots & \\
\rho_{n 1} \sigma_n \sigma_1 & \rho_{n 2} \sigma_2 \sigma_n & \ldots & \sigma_n^2
\end{array}\right]
$$

I can then just decompose the matrix into three matrices by the law of association and get

$$
\boldsymbol{\Sigma}=\left[\begin{array}{llll}
\sigma_1 & & & \\
& \sigma_2 & & \\
& & \ddots & \\
& & & \sigma_n
\end{array}\right]\left[\begin{array}{cccc}
1 & \rho_{12} & \ldots & \rho_{1 n} \\
\rho_{21} & 1 & \ldots & \rho_{2 n} \\
\vdots & \vdots & \ddots & \vdots \\
\rho_{n 1} & \rho_{n 2} & \ldots & 1
\end{array}\right]\left[\begin{array}{llll}
\sigma_1 & & & \\
& \sigma_2 & & \\
& & \ddots & \\
& & & \sigma_n
\end{array}\right]
$$
Which just gives me the standard deviations for both RVs as the outside matrices and the correlation matrix in the middle. 

I can now use the neat aspect of diagonal matrices, that their inverse is just the reciprocal of the diagonal elements, to obtain a clear path to obtaining the correlation matrix. 

$$
\mathbf{C}:=\left[\begin{array}{lll}
1 / \sigma_1 & & \\
& \ddots & \\
& & 1 / \sigma_n
\end{array}\right] \boldsymbol{\Sigma}\left[\begin{array}{lll}
1 / \sigma_1 & & \\
& \ddots & \\
& & 1 / \sigma_n
\end{array}\right]
$$
`Note: Should the correlation matrix only contain values between 0 and 1?`

## Properties


## Summary Statistics
### Total Variance

$$
\sigma_{\mathrm{tv}}^2:=\operatorname{tr}(\boldsymbol{\Sigma})=\sum_{i=1}^n \sigma_i^2
$$


### Generalised Variance

$$
\sigma_{\mathrm{gv}}^2:=\operatorname{det}(\boldsymbol{\Sigma})=|\boldsymbol{\Sigma}|
$$











