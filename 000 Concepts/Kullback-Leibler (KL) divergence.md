---
title: Kullback-Leibler (KL) divergence
date: 19-05-2023
time: 12:11
author: Luca Trautmann
tags:
  - Mathematics
  - ML
series: Information Theory
chapter: 1
modified: 2024-04-05
---

> [!Rule]+
> $$D_{KL}(P||Q) = \begin{cases}\sum_{i} P(i) \log \frac{P(i)}{Q(i)} &
> \text{if discrete} \\ 
> \int P(x) \log \frac{P(x)}{Q(x)} dx & \text{if continuous}
> \end{cases}$$

# Kullback-Leibler (KL) divergence

The Kullback-Leibler divergence, often simply referred to as KL divergence, is a measure that quantifies the "distance" between two probability distributions. It offers a method for gauging how far apart two random variables are, giving us a way to contrast different estimations of a probability distribution.

## Example: Weather / Bernoulli

To illustrate how this works, let's consider an example. Suppose we have a binary variable for weather, W, where there are only two outcomes: the weather is good or the weather is bad. If we encode good weather as 1 and bad weather as 0, this means our weather variable W can take values in the set {0, 1}. Therefore, we can say the weather follows a Bernoulli distribution, expressed as $W \sim \text{Bernoulli} (\theta)$, where $\theta$ is the probability of good weather.

Now, imagine there are two individuals with differing opinions on the likelihood of good weather. One person believes that $\theta$ is 0.8, implying that the weather distribution, $P(W)$, is $W \sim \text{Bernoulli} (0.8)$. The other person, on the other hand, believes that $\theta$ is actually 0.7, hence $P(W) = W \sim \text{Bernoulli} (0.7)$. 

We can apply the KL divergence to calculate how far apart these two distributions are. Given that our example involves a discrete distribution, we would use the discrete form of the KL divergence. This is defined as $D_{KL}(P||Q) = \sum_{w} P(w) \log \frac{P(w)}{Q(w)}$, where P and Q are the two probability distributions we're comparing.

For a Bernoulli distribution, the possible values that W can take are 0 and 1. The expression gives the probability of each value in a Bernoulli distribution $\theta^w(1-\theta)^{1-w}$, where w is the value taken by the random variable W. 

Let's extend the discussion by actually calculating the KL divergence.

To start, let's label our two distributions. Let $P$ Be the distribution according to the first person's belief, i.e., $P(W) \sim \text{Bernoulli}(0.8)$, and $Q$ be the distribution according to the second person's belief, i.e., $Q(W) \sim \text{Bernoulli}(0.7)$. Here, $P(w)$ and $Q(w)$ represent the probability of occurrence of weather $w$ according to the two people, respectively.

The KL divergence of $Q$ from $P$ is then given by:

$$
D_{KL}(P||Q) = \sum_{w} P(w) \log \frac{P(w)}{Q(w)}
$$

As noted, the possible values that $W$ Can take are 0 and 1. Therefore, this expression can be broken down into two terms:

$$
D_{KL}(P||Q) = P(W=1) \log \frac{P(W=1)}{Q(W=1)} + P(W=0) \log \frac{P(W=0)}{Q(W=0)}
$$

Substituting the Bernoulli distribution probabilities, we have:

$$
D_{KL}(P||Q) = [P(W=1) \log \frac{0.8}{0.7}] + [P(W=0) \log \frac{0.2}{0.3}]
$$

Given $P(W=1) = 0.8$ and $P(W=0) = 0.2$, we can substitute these values to get:

$$
D_{KL}(P||Q) = [0.8 \log \frac{0.8}{0.7}] + [0.2 \log \frac{0.2}{0.3}]
$$

This is the expression for the KL divergence between $P$ and $Q$. To obtain the numerical value, we calculate the expression.
$$D_{KL}(P||Q) \approx 0.26$$

## Relative Information
If we minimise the KL divergence between two densities, we are minimising the relative information between the two distributions.

### Information Entropy - First Principles:
A random variable, contains information. The _information_ received from a random variable taking a particular value can be viewed as a measure of our “surprise” about that value. 

Low information is not surprising; high information is surprising. Now imagine I didn’t know or couldn’t remember the equation for information. What would be a sensible formulation?

1. It makes sense that information is a monotonic function of probability. Higher probability means strictly lower information. For example, rolling a die and getting an even number should be less surprising than rolling a die and getting a 2.

2. Information should be additive for independent events. If I roll a die and flip a coin, my total information should be some additive combination of the two probabilities.

These two principles should make the formula for information clearer for me: 

$$
h(x)=-\log p(x) \quad H(X)=\mathbb{E}[h(x)]
$$

We can also prove that two independent events are additive:

$$
\begin{aligned}
h(x, y) & =-\log p(x, y) \\
& =-\log \{p(x) p(y)\} \\
& =-\log p(x)-\log p(y) \\
& =h(x)+h(y)
\end{aligned}
$$

decomposing the KL divergence in a similar fashion, shows me the analogous property.

$$
\begin{aligned}
D_{\mathrm{KL}}[P \| Q] & =\int_{-\infty}^{\infty} p(x) \log \frac{p(x)}{q(x)} d x \\
& =\mathbb{E}_{p(x)}\left[\log \frac{p(x)}{q(x)}\right] \\
& =\mathbb{E}_{p(x)}[\log p(x)-\log q(x)] \\
& =\mathbb{E}_{p(x)}[-\log q(x)]-\mathbb{E}_{p(x)}[-\log p(x)] \\
& =H(Q)-H(P)
\end{aligned}
$$


## Non-negativity of the KL divergence
But why does _minimizing_ the KL divergence between two densities—as in variational inference—guarantee that our optimization objective is performing density estimation? The answer to this relies on the convexity of logarithms and Jensen’s inequality.

