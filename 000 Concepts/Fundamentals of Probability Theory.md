---
title: Fundamentals of Probability Theory
date: 07-12-2023
time: 15:59
output: meansquarederror.xyz
author: Luca Trautmann
tags:
  - Statistics
---
based of: [[000 Background Probability Theory]] and [[@park2019]] as well as [Probability for Scientists](https://betanalpha.github.io/assets/case_studies/probability_theory.html#2_mathematical_logistics)
# Fundamentals of Probability Theory
The basic idea behind the basic of probability theory can be summarised in an outrageously compressed form in the following collection of symbols: 

$$\left [\Omega, \mathcal{F}_{\sigma}, X^{-1}, X_{\mathbb{R}}, \mathbb{P}_{[0,1]} \right ]$$

Where: 
- $\Omega$ : The sample space.
- $\mathcal{F}_\sigma$ : The $\sigma$-algebra on $\Omega$, defining measurable events.
- $X^{-1}$ : The pre-image operation under the random variable, illustrating how events are generated from the outcomes mapped by $X$.
- $X_{\mathbb{R}}$ : The random variable itself, mapping outcomes in $\Omega$ to real numbers in $\mathbb{R}$.
- $\mathbb{P}_{[0,1]}$ : The probability measure, assigning probabilities to events into the range of $[0, 1]$.

Alternatively, it is expressed, more regularly: 
$$\left [ \Omega, \mathcal{F}, \mathbb{P} \right ]$$

## Juicy Details
Great five symbols that all do not scream enlightenment on their own. So what do they mean. Start with the sample space $\omega$. It is the space that contains all possible outcomes of the experiment under consideration. The problem with the sample space is that the sets contained in it do not all behave well (see. Axiom of choice). 

In full the chain of events can then be explicitly stated as:

> __Beginning with a sample space $\Omega$, we define a $\sigma$-algebra $\mathcal{F}$ to get a well-defined set of events. On the so created set we define a random variable $X$ and use the pre-image to map from the well-defined event space to the real number line. Lastly, we employ a probability measure, which assigns probabilities in the interval $[0,1]$ to these events, quantifying the likelihood of each occurrence defined by the random variable.__

