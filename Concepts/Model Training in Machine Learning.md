---
title: Model Training in Machine Learning
date: 31-05-2023
time: 14:57
author: Luca Trautmann
tags: ["ML"]
series: "Machine Learning Fundamentals"
chapter: 7
---

>[!Rule]+
>Step 1. Compute the derivatives of the loss with respect to the parameters:
> $$\frac{\partial L}{\partial \boldsymbol{\phi}}=\left[\begin{array}{c}\frac{\partial L}{\partial \phi_0} \\\frac{\partial L}{\partial \phi_1} \\\vdots \\\frac{\partial L}{\partial \phi_N}\end{array}\right]$$
> Step 2. Update the parameters according to the rule:
> $$\phi \longleftarrow \phi-\alpha \cdot \frac{\partial L}{\partial \phi}$$
> where the positive scalar $\alpha$ is the learning rate.

> [!important Note]
> The gradient step for any parameter is the__ sum of the loss values__ for all the training examples. 
> $$\frac{\partial L}{\partial \phi} = \frac{\partial}{\partial \phi} \sum^I_{i=1} \ell_i = \sum^I_{i=1} \frac{\partial \ell_i}{\partial \phi}$$
> It is therefore of paramount importance to update the parameter after all the included training examples have been calculated and not in between the calculations. 

# Model Training in Machine Learning
## Gradient Descent
We usually won't be able to find analytical solutions for optimising the model that has been constructed. To train the model we have to minimise the loss function (see [[Parameterisating Conditional Distributions with Neural Networks]]).
 $$
\hat{\phi}=\underset{\phi}{\operatorname{argmin}}[\mathrm{L}[\phi]] .
$$
usually we do this iteratively with gradient optimisation methods such as gradient descent or stochastic gradient descent. The following gives the general recipe for these iterative optimisations:

## Types of Optimisation Algorithms (incomplete)
There are several optimisation algorithms that are frequently used in deep learning. Here are some of the most commonly used algorithms:

1. __Gradient Descent (GD):__ The standard optimisation algorithm used in deep learning is Gradient Descent. GD is a first-order optimisation algorithm that updates the parameters of the model in the direction of the negative gradient of the loss function. The update rule for GD is given by:

$$\theta_{t+1} = \theta_t - \alpha \nabla_{\theta_t} J(\theta_t)$$

where $\theta_t$ is the parameter vector at time step $t$, $\alpha$ is the learning rate, and $\nabla_{\theta_t} J(\theta_t)$ is the gradient of the loss function with respect to the parameter vector at time step $t$.

2. __Stochastic Gradient Descent (SGD):__ SGD is a variant of GD that uses a random sample of data points to estimate the gradient at each time step. The update rule for SGD is given by:

$$\theta_{t+1} = \theta_t - \alpha \nabla_{\theta_t} J(\theta_t; x_i, y_i)$$

where $x_i$ and $y_i$ are randomly selected data points from the dataset.

3.__Adam:__ Adam is an adaptive learning rate optimisation algorithm that computes individual learning rates for different parameters based on estimates of the second moment of the gradients. The update rule for Adam is given by:

$$m_t = \beta_1 m_{t-1} + (1 - \beta_1) \nabla_{\theta_t} J(\theta_t)$$

$$v_t = \beta_2 v_{t-1} + (1 - \beta_2) (\nabla_{\theta_t} J(\theta_t))^2$$

$$\theta_{t+1} = \theta_t - \alpha \frac{m_t}{\sqrt{v_t} + \epsilon}$$

where $m_t$ and $v_t$ are estimates of the first and second moments of the gradients, $\beta_1$ and $\beta_2$ are the exponential decay rates for the moment estimates, and $\epsilon$ is a small constant to prevent division by zero.

4. __Adagrad:__ Adagrad is an adaptive learning rate optimization algorithm that adapts the learning rate of each parameter based on the historical gradient information. The update rule for Adagrad is given by:

$$g_{t,i} = (\nabla_{\theta_t} J(\theta_t))_i^2$$

$$\theta_{t+1,i} = \theta_{t,i} - \frac{\alpha}{\sqrt{\sum_{j=1}^t g_{j,i}}} (\nabla_{\theta_t} J(\theta_t))_i$$

where $g_{t,i}$ is the sum of the squared gradients for parameter $i$ up to time step $t$.

