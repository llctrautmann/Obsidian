---
title: Probability and Distributions
date:
  - 15-04-2024
time: 20:02
author: Luca Trautmann
tags:
  - "#ML"
series: M4ML
chapter: 6
status: Incomplete
modified: 2024-04-15
---
# Probability and Distributions
## Construction of a Probability Space
Probability aims at defining a mathematical structure to describe random outcomes of experiments. Using this mathematical structure of probability, the goal is to perform automated reasoning, and in this sense, probability generalizes logical reasoning.

Because it is not possible to perform some operation with boolean logic, probability theory can be considered a generalisation of Boolean logic. In the context of machine learning, it is often applied in this way to formalize the design of automated reasoning systems.

### Three basic claimes about probability
1. The degrees of plausibility are represented by real numbers
2. These must be based on the rules of common sense
3. The resulting reasoning must be consistent with the three following meanings of the word "consistent":
	1. <mark class="hltr-orange">Consistency or non-contradiction</mark>: When the same result can be reached through different means, the same plausibility value must be found in all cases
	2. <mark class="hltr-orange">Honesty</mark>: All available data must be taken into account
	3. <mark class="hltr-orange">Reproducibility</mark>: If our state of knowledge about two problems are the same, then we must assign the same degree of plausibility to both of them. 

There are two major schools of probability (see [[Probability Theory Definitions]]): Frequentist and Bayesian

## Probability and Random Variables
Modern probability is based on the Kolmogorov Theorems of Probability [[000 Background Probability Theory#Kolmogorov Axioms / Axioms of Probability]].

**The sample space $\Omega$**
The sample space is the set of all possible outcomes of the experiment, usually denoted by $\Omega$. For example, two successive coin tosses have a sample space of $\{\mathrm{hh}, \mathrm{tt}, \mathrm{ht}, \mathrm{th}\}$, where "h" denotes "heads" and "t" denotes "tails".

**The event space $\mathcal{A}$**
The event space is the space of potential results of the experiment. A subset $A$ of the sample space $\Omega$ is in the event space $\mathcal{A}$ if at the end of the experiment we can observe whether a particular outcome $\omega \in \Omega$ is in $A$. The event space $\mathcal{A}$ is obtained by considering the collection of subsets of $\Omega$, and for discrete probability distributions (Section 6.2.1) $\mathcal{A}$ is often the power set of $\Omega$.

**The probability $P$**
With each event $A \in \mathcal{A}$, we associate a number $P(A)$ that measures the probability or degree of belief that the event will occur. $P(A)$ is called the probability of $A$.

This all relates to set theory [[Sets in Mathematics]], [[000 Background Probability Theory]]. 