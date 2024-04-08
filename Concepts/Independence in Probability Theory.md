---
title: Independence in Probability Theory
date: 20-05-2023
time: 17:51
author: Luca Trautmann
tags: ['Mathematics']
series: "Probability Theory"
chapter: 6
---

# Independence in Probability Theory
## Independence

When we discuss independence in probability theory, it means that the occurrence of one event does not affect the occurrence of another event. In the context of random variables, two random variables X and Y are said to be independent if the joint probability distribution can be expressed as the product of their individual probability distributions.

This is mathematically represented as $X \perp Y$ implying $p(X,Y) = p(X)p(Y)$ where $p(X,Y)$ is the joint probability of X and Y, and $p(X)$ and $p(Y)$ are the marginal probabilities of X and Y respectively.

The more general form of this for a set of random variables $X_1, X_2, ..., X_m$ is that they are independent if and only if the joint probability distribution can be expressed as the product of their marginal probability distributions, i.e. $$p(X_1, ... , X_m) = \prod_{i=1}^m p(X_i)$$It's important to note that this general principle has to apply to all subset of these random variables for independence. 

## Conditional Independence

In many real-world situations, variables are not completely independent of each other because they might influence each other indirectly. That's where the concept of conditional independence comes in.

Conditional independence describes the relationship between two variables that are independent, given the condition or knowledge of a third variable. In other words, two variables X and Y are conditionally independent given a third variable Z if the conditional joint probability of X and Y, given Z, equals the product of the conditional probabilities of X and Y, given Z.

This can be mathematically represented as $X \perp Y | Z$ implying $p(X,Y|Z) = p(X|Z)p(Y|Z)$.

This concept of conditional independence corresponds to a full mediation model in causal inference. In this model, the third variable Z completely mediates or explains the relationship between X and Y. This can be depicted graphically as $X - Z - Y$, where the arrows represent the causal relationships and suggest that X influences Y entirely through its effect on Z.

This conditional independence is a central concept in many areas of statistics and machine learning, including Bayesian networks, Markov models, and causal inference.