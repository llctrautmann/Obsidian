---
title: Parameterizing Conditional Distributions with Neural Networks
date: 29-05-2023
time: 10:02
author: Luca Trautmann
tags: ['ML','VAE']
series: Machine Learning Fundamentals
chapter: 1
---



> [!Rule]+
> The recipe for constructing loss functions for training data $\left\{\mathbf{x}_i, \mathbf{y}_i\right\}$ using the maximum likelihood approach is hence:
> 1. Choose a suitable probability distribution $\operatorname{Pr}(\mathbf{y} \mid \boldsymbol{\theta})$ defined over the domain of the predictions $\mathbf{y}$ with distribution parameters $\boldsymbol{\theta}$.
> 2. Set the machine learning model $\mathbf{f}[\mathbf{x}, \boldsymbol{\phi}]$ to predict one or more of these parameters, so $\boldsymbol{\theta}=\mathbf{f}[\mathbf{x}, \boldsymbol{\phi}]$ and $\operatorname{Pr}(\mathbf{y} \mid \boldsymbol{\theta})=\operatorname{Pr}(\mathbf{y} \mid \mathbf{f}[\mathbf{x}, \boldsymbol{\phi}])$.
> 3. To train the model, find the network parameters $\hat{\phi}$ that minimise the negative log-likelihood loss function over the training dataset pairs $\left\{\mathbf{x}_i, \mathbf{y}_i\right\}$ :
> $$\hat{\boldsymbol{\phi}}=\underset{\phi}{\operatorname{argmin}}[L[\phi]]=\underset{\phi}{\operatorname{argmin}}\left[-\sum_{i=1}^I \log \left[\operatorname{Pr}\left(\mathbf{y}_i \mid \mathbf{f}\left[\mathbf{x}_i, \boldsymbol{\phi}\right]\right)\right]\right]$$
> 4. To perform inference for a new test example $\mathbf{x}$, return either the full distribution $\operatorname{Pr}(\mathbf{y} \mid \mathbf{f}[\mathbf{x}, \hat{\boldsymbol{\phi}}])$ or some statistic of this distribution.

>[!Formula]+
>$$L[\phi]  =-\sum_{i=1}^I \log \left[\operatorname{P}\left(y_i \mid \mathrm{f}\left[\mathbf{x}_i, \phi\right], \sigma^2\right)\right]$$
>Replace $P$ with the appropriate likelihood function.

# Parameterising Conditional Distributions with Neural Networks
## Maximum Likelihood
- Instead of calculating concrete values for the the model output, modern deep learning solutions calculate conditional probability distributions (see: [[Interactions between Random Variables]]) over the output $y$ given the inputs $x$.
- Hence, the loss encourages each training output $y_i$ to have a high probability under the distribution $P(y_i|x_i)$ computed from the input $x_i$
- to do so we need to choose a parametric distribution (e.g. $\mathcal{N}$ or $\mathcal{U}$) defined on the output domain. The network then calculates one or more parameter(s) of the distributions. 

## Maximum Likelihood Criterion
- For each training example the model now computes different distribution parameters $\boldsymbol{\theta}_i=\mathbf{f}\left[\mathbf{x}_i, \boldsymbol{\phi}\right]$
- Each training example should have a high probability under its corresponding distribution $P(y_{i}| \theta_{i})$ 
- For all training examples we then maximise the combined probability across all $I$ training examples:
$$
\begin{aligned}
\hat{\boldsymbol{\phi}} & =\underset{\phi}{\operatorname{argmax}}\left[\prod_{i=1}^I \operatorname{P}\left(\mathbf{y}_i \mid \mathbf{x}_i\right)\right] \\
& =\underset{\phi}{\operatorname{argmax}}\left[\prod_{i=1}^I \operatorname{P}\left(\mathbf{y}_i \mid \boldsymbol{\theta}_i\right)\right] \\
& =\underset{\phi}{\operatorname{argmax}}\left[\prod_{i=1}^I \operatorname{P}\left(\mathbf{y}_i \mid \mathbf{f}\left[\mathbf{x}_i, \boldsymbol{\phi}\right]\right)\right] .
\end{aligned}
$$
- The combined term is the likelihood of the parameters and is called the <mark style="background: #FFB8EBA6;">maximum likelihood criterion</mark>.
- This required the assumptions that the data points are <mark style="background: #FFB8EBA6;">independent and identically distribution (i.i.d)</mark>.

## Maximising the log-likelihood
- the likelihood terms are multiplications across all training examples. This leads to very small values.
- To circumvent this problem, it is useful to take the logarithm of the joint likelihood. This turns the multiplication into sums. 
- It also works because the logarithm is a monotonically increasing function: if $z > z'$ then $\text{log}[z] > \text{log}[z']$ and vice versa
- It follows that when we change the model parameters $\phi$ to improve the log-likelihood criterion, we also improve the original maximum likelihood criterion
- It also follows that the overall maxima of the two criteria must be in the same place, so the best model parameters $\hat{\phi}$ are the same in both cases.
- To keep with convention, loss functions are minimised and hence instead of maximising the log-likelihood, we minimise the negative log-likelihood
$$
\begin{aligned}
\hat{\boldsymbol{\phi}} & =\underset{\phi}{\operatorname{argmin}}\left[-\sum_{i=1}^I \log \left[\operatorname{P}\left(\mathbf{y}_i \mid \mathbf{f}\left[\mathbf{x}_i, \boldsymbol{\phi}\right]\right)\right]\right] \\\\
& =\underset{\phi}{\operatorname{argmin}}[\mathrm{L}[\boldsymbol{\phi}]],
\end{aligned}
$$

## Inference
- The network does now not predict the outputs $y$ but instead determines a distribution over $y$. To get a concrete estimate we can return summary statistics of the newly created distributions such as the mean for the standard normal distribution (see: [[Moments of a Distribution]]). 



## Deriving MSE from the Normal Distribution  $\mathcal{N}$ for univariate Regression
The formula for the standard normal distribution is given below:
$$P(y|\mu,\sigma^2) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(y-\mu)^2}{2\sigma^2}} \quad \text{for } y \in \mathbb{R}$$
Lets assume that our model $f[x,\phi]$ is not predicting real values but the parameters of distributions $\theta$. Hence, we can write that $\mu = f[x,\phi]$ and in combination with the PDF for the standard normal:
$$
\operatorname{P}\left(y \mid \mathrm{f}[\mathbf{x}, \phi], \sigma^2\right)=\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left[-\frac{(y-\mathrm{f}[\mathbf{x}, \phi])^2}{2 \sigma^2}\right]
$$
Next we aim to find the best parameters $\phi$ that make the training data most probable under the distribution. Hence we create a loss function based on the negative log-likelihood:
$$
\begin{aligned}
L[\phi] & =-\sum_{i=1}^I \log \left[\operatorname{P}\left(y_i \mid \mathrm{f}\left[\mathbf{x}_i, \phi\right], \sigma^2\right)\right] \\
& =-\sum_{i=1}^I \log \left[\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left[-\frac{\left(y_i-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right)^2}{2 \sigma^2}\right]\right] .
\end{aligned}
$$
With some algebraic manipulation the loss function can be reduced to the formula for the Mean squared error
$$
**\begin{aligned}
\hat{\phi} & =\underset{\phi}{\operatorname{argmin}}\left[-\sum_{i=1}^I \log \left[\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left[-\frac{\left(y_i-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right)^2}{2 \sigma^2}\right]\right]\right]  \quad \text{log rule: } log(ab) = log(a) + log(b) \\
& =\underset{\phi}{\operatorname{argmin}}\left[-\sum_{i=1}^I \log \left[\frac{1}{\sqrt{2 \pi \sigma^2}}\right]-\frac{\left(y_i-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right)^2}{2 \sigma^2}\right] \quad \text{remove constant log term}  \\
& =\underset{\phi}{\operatorname{argmin}}\left[-\sum_{i=1}^I-\frac{\left(y_i-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right)^2}{2 \sigma^2}\right] \quad \text{remove constant variance term} \\
& =\underset{\phi}{\operatorname{argmin}}\left[\sum_{i=1}^I\left(y_i-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right)^2\right],
\end{aligned}**
$$
So we can therefore deduce, that for univariate regression examples, predicting the mean of a standard normal distribution eventually boils down to mean squared error between the target $y_i$ and the model output $f[x,\phi]$.


## Other Data Types
In this chapter, we have focused on regression and classification because these problems are widespread. However, to make different types of predictions, we simply choose an appropriate distribution over that domain and apply the recipe



# Series
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```



