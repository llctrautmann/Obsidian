---
title: Variance of the sum of RVs
date:
  - 08-04-2024
time: 15:46
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-05-06
---
# Variance of the sum of RVs
**Theorem**: The variance of the sum of two random variables equals the sum of the variances of those random variables, plus two times their covariance:
$$
\operatorname{Var}(X+Y)=\operatorname{Var}(X)+\operatorname{Var}(Y)+2 \operatorname{Cov}(X, Y) .
$$


**Proof**: The variance is defined in terms of the expected value as
$$
\operatorname{Var}(X)=\mathrm{E}\left[(X-\mathrm{E}(X))^2\right] .
\tag{1}$$

Using this and the linearity of the expected value, we can derive (1) as follows:
$$
\begin{aligned}
\operatorname{Var}(X+Y) & \stackrel{(2)}{=} \mathrm{E}\left[((X+Y)-\mathrm{E}(X+Y))^2\right] \\
& =\mathrm{E}\left[([X-\mathrm{E}(X)]+[Y-\mathrm{E}(Y)])^2\right] \\
& =\mathrm{E}\left[(X-\mathrm{E}(X))^2+(Y-\mathrm{E}(Y))^2+2(X-\mathrm{E}(X))(Y-\mathrm{E}(Y))\right] \\
& =\mathrm{E}\left[(X-\mathrm{E}(X))^2\right]+\mathrm{E}\left[(Y-\mathrm{E}(Y))^2\right]+\mathrm{E}[2(X-\mathrm{E}(X))(Y-\mathrm{E}(Y))] \\
& \stackrel{(2)}{=} \operatorname{Var}(X)+\operatorname{Var}(Y)+2 \operatorname{Cov}(X, Y) .
\end{aligned}
$$

