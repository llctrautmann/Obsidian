---
title: Markov Chain Monte Carlo
date: 19-05-2023
time: 14:52
author: Luca Trautmann
tags: ['ML']
series: "Mathematics & Statistics"
chapter: 3
---

# Markov Chain Monte Carlo

Markov Chain Monte Carlo methods are a class of algorithms used to sample from a probability distribution, especially in Bayesian statistics for approximating the posterior distribution. 

Let's say we have data $D$, a model parameterized by $\theta$, and we're interested in the posterior distribution $P(\theta | D)$ given by Bayes' theorem as:

$$ P(\theta | D) = \frac{P(D | \theta) P(\theta)}{P(D)} $$

In practice, it's hard to compute $P(D)$, so we instead consider the unnormalized distribution $P(D | \theta) P(\theta)$ and sample $\theta$ values from this using MCMC methods.

A key idea in MCMC is to construct a Markov chain with a stationary distribution equal to the target distribution. One commonly used MCMC algorithm is the Metropolis-Hastings (MH) algorithm.

Given a current state $\theta^{(t)}$, the MH algorithm generates a new state $\theta^{(t+1)}$ as follows:

1. Propose a candidate for the next state $\theta^*$ from a proposal distribution $Q(\theta^* | \theta^{(t)})$.
2. Compute the acceptance probability:
$$ a = min\left(1, \frac{P(\theta^* | D) / Q(\theta^* | \theta^{(t)})}{P(\theta^{(t)} | D) / Q(\theta^{(t)} | \theta^*)}\right) $$
3. Accept the candidate $\theta^*$ as the next state with probability $a$; otherwise, the next state is the same as the current state.

In this way, the MH algorithm generates a sequence of states (a Markov chain) that, given enough time, will converge to the target distribution $P(\theta | D)$.

There are also more sophisticated MCMC algorithms like Gibbs sampling, Hamiltonian Monte Carlo, and others, which have various advantages and may be more suitable depending on the specific problem.

In summary, MCMC methods are powerful tools for Bayesian inference, allowing us to approximate posterior distributions that would be computationally prohibitive to calculate exactly.
