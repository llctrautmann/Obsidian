---
title: Probability as an Extension of Boolean Logic
date:
  - 29-06-2024
time: 16:18
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-29
---
# Probability as an Extension of Boolean Logic

## Intro and Background
Probability theory is rooted in set theory as outlined in the [[000 Background Probability Theory|fundamentals]]. 

The most important thing to understand is:
- Events are sets in the sample space. 
- These sets need to be transformed into numbers between 0 and 1. 
- This transformation requires some guardrails which is the sigma algebra
- A probability distribution defined by Kolmogorov's axioms is completely specified by the probability triplet $(\Omega, \mathcal{F}, \mathbb{P})$
- In such cases we always assume a valid $\sigma$-algebra underlying the entire thing to exclude ill-formed sets. Condensed into symbols the entire derivation of then fundamentals of probability theory can be can be summarised with the following symbols:

$$\Large\tag{1}(\Omega, \mathcal{F}, \mathbb{P})$$
- $\Omega$ is the sample space
- $\mathcal{F}$ is the sigma algebra
- $\mathbb{P}$ is the probability measure

## An Event
An event can be any occurance or statement like the following:

- _"Tomorrow it will rain."_

## Probability of an Event
We denote a probability as $P(\cdot)$. For example the probability that the event $A$ = _"Tomorrow it will rain."_ occurs is $P(A)$.   
## Basic Probability Rules
There are three cases that are important [^1]:
1. Union
	1. Independent: $P(A \cap B) = P(A) \cdot P(B)$
	2. Dependent: $P(A \cap B) = P(A) \cdot P(B|A) = P(B) \cdot P(A|B)$
2. Intersection: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
3. Condition

# Footnotes
[^1]: A lot on the background in [[jaynes2003.pdf]]