---
title: PhD Presentation Script
date:
  - 14-03-2024
time: 09:49
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-03-14
---
# PhD Presentation Script


## Introduction
The two articles highlight a bit of a trend that goes a bit like this: 
- Doing a PhD at a university is pointless because the amount of compute available to companies like google is so far outmatching university research that 


## Propagation of Downstream Models

- Model outputs a vector of means and variances for each pixel. 
- Sampling from these distributions with the upstream model but different samples is akin to MC sampling to approximate the mean and variance. 
- These values are then combined to provide a mean and a variance of the downstream regression model $N(E(y)| Var(Y))$

## Weighing of Val Losses
- based of the following formula: 
$$
w_i\left(\theta_i, V\right)=\left(\frac{1}{L_{\theta_i}+\frac{r L_{\max }-L_{\min }}{1-r}}\right) /\left(\sum_{j=1}^N \frac{1}{L_{\theta_j}+\frac{r L_{\max }-L_{\min }}{1-r}}\right) \quad \forall i \in\{1, \ldots, N\}
$$

$$
\frac{\min \left(\left(w_i\right)_{i=1}^N\right)}{\max \left(\left(w_i\right)_{i=1}^N\right)}=r \in(0,1) \quad 0<w_i\left(\theta_i, D\right)<1 \quad \forall i \in\{1, \ldots, N\}, \quad \sum_{i=1}^N w_i\left(\theta_i, D\right)=1
$$


## First Project




