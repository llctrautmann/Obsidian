---
author: Garrett Thomas
tags:
  - "#ML"
  - LinAlg
  - Probability
  - "#Mathematics"
Docstring:
  - This document is an attempt to provide a summary of the mathematical background needed for an introductory class in machine learning.
url: 
year: 2018
date:
  - 10-05-2024
time: 10:36
modified: 2024-07-02
---

# Probability
## Basics
- $\Omega$ is the sample space - the set of all possible outcomes for a randomised expeiment
	- $\mathbb{P}(\Omega)=1$
	- Countable additivity: $\mathbb{P}\left(\bigcup_i A_i\right)=\sum_i \mathbb{P}\left(A_i\right)$
- The triplet ($\Omega, \mathcal{F}, \mathbb{P}$) defines the probability space. 

### Basic Axioms that follow 
- $P(A^{C})=1-\mathbb{P}(A)$ 
- $\forall B_i \subseteq A, \mathbb{P}(B) \leq \mathbb{P}(A)$ 
- $0=\mathbb{P}(\varnothing) \leq \mathbb{P}(A) \leq \mathbb{P}(\Omega)=1$

### OR
- $\mathbb{P}(A \cup B)=\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(A \cap B)$
- for disjoint and non-disjoint sets $\mathbb{P}\left(\bigcup_i A_i\right) \leq \sum_i \mathbb{P}\left(A_i\right)$

### CONDITIONAL
- $\mathbb{P}(A \mid B)=\frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}$
	- this makes sense because we need the ration of $B$ in which $A$ is also true. 


### AND (Chain Rule)
- $\mathbb{P}(A \cap B)=\mathbb{P}(A \mid B) \mathbb{P}(B)=\mathbb{P}(B \mid A) \mathbb{P}(A)$
	- Follow logically from the conditional probabilities

### BAYES
- [[Bayes Theorem]] follows logically from the symmetry of AND statements. 
	- $\mathbb{P}(A \mid B)=\frac{\mathbb{P}(B \mid A) \mathbb{P}(A)}{\mathbb{P}(B)}$
	- without normalisation: $\mathbb{P}(A \mid B) \propto \mathbb{P}(A) \mathbb{P}(B \mid A)$
	- Under this formulation, $\mathbb{P}(A)$ is often referred to as the prior, $\mathbb{P}(A \mid B)$ as the posterior, and $\mathbb{P}(B \mid A)$ as the likelihood.

## Random Variables
- RVs are functions from the sample space to the real line $X: \Omega\rightarrow \mathbb{R}$ [^1]. 

### CDF
- The CDF gives the probability that a random variables is **at most** a certain value:
	- $F(x)=\mathbb{P}(X \leq x)$
	- $\mathbb{P}(a<X \leq b)=F(b)-F(a)$ for ranges

### Discrete Random Variables
- requires a countable range for the outcomes of a random variable
- the probability mass function $p: X(\Omega) \rightarrow[0,1]$ defines the RV
	- $\sum_{x \in X(\Omega)} p(x)=1$ 
	- $\mathbb{P}(X=x)=p(x)$ 

### Continuous Random Variables
- In the continuous case there are no countable ranges and the probability of each specific value is 0.
- most CRVs are absolute CRVs and are defined between 0 and $\infty$: $p: \mathbb{R} \rightarrow[0, \infty)$
- continuous RVs are defined with [[Probability Density Function|pdf]]s
	-  $F(x) \equiv \int_{-\infty}^x p(z) \mathrm{d} z$
	- $\int_{-\infty}^{\infty} p(x) \mathrm{d} x=1$ 
		- values can exceed 1 as long as the area is 1. 
	- $\mathbb{P}(a \leq X \leq b)=\int_a^b p(x) \mathrm{d} x$
	- $p(x)=F^{\prime}(x)$

## Joint Distributions
- Joints are distributions over multiple RVs
	- $p\left(X_1, \ldots, X_n\right)$
	- 

### Independence of RVs
- basic probabilities teach that two probabilities are independent if the joint is the product of the individual probabilities
	- 

### Marginal Distributions

## Ex

# Footnotes

[^1]: [[Thomas2018.pdf#page=39&selection=64,0,71,15&color=yellow|Thomas2018, p.39]]