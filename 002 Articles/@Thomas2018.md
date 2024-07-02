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


# Footnotes

[^1]: [[Thomas2018.pdf#page=39&selection=64,0,71,15&color=yellow|Thomas2018, p.39]]