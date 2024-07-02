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
	- $p(X, Y)=p(X) p(Y)$
	- $p\left(X_{i_1}, \ldots, X_{i_k}\right)=\prod_{j=1}^k p\left(X_{i_j}\right)$ requires all pairwise combinations of RVs to be independent as well
	- to make the math more bearable it is often assumed that RVs are i.i.d. But that is a hard assumption that is in many cases not fully congruent with reality
		- [[@feiner2023]] is a good example where this is assumed on a pixel-wise level, but not true in reality as the structures in the brain do have cross dependencies that are deliberately removed to ease modelling. 

### Marginal Distributions
- Marginalisation removes RVs from joint distributions either by summation or by integration
- $p(X)=\sum_y p(X, y)$

## Great Expectations
- There are two formulae for expected values
	- $\mathbb{E}[X]=\sum_{x \in X(\Omega)} x p(x)$ (discrete)
	- $\mathbb{E}[X]=\int_{-\infty}^{\infty} x p(x) \mathrm{d} x$ (continuous)

### Properties of EVs
- $\mathbb{E}\left[\sum_{i=1}^n \alpha_i X_i+\beta\right]=\sum_{i=1}^n \alpha_i \mathbb{E}\left[X_i\right]+\beta$
	- For linear transformation this holds independently of whether RVs are dependent of each other or not


## Variance
- Variance measures the spread around the centre of the distribution
	- $Var(\mathbf{X})= \mathbb{E}\left[(X-\mathbb{E}\left[\mathbf{X}\right])^2\right]=\mathbb{E}\left[X^2\right]-\mathbb{E}[X]^2$

### Properties of Variance
- variance is by definition not linear [^2], but it can be shown that 
	- $\operatorname{Var}(\alpha X+\beta)=\alpha^2 \operatorname{Var}(X)$ 
		- multiplicative constants get squared and any additive are removed [^3].

### Standard Deviation
- sqrt of the variance allows for units of the RV to be the same as the Standard deviation; unlike the variance
	- $\sqrt{ \operatorname{Var}(X) }$ 

## Covariance
- measure of linear relationship between two random variables
	- 
# Optimisation
## Estimation of Parameters
### MLE

### MAP
# Footnotes

[^1]: [[Thomas2018.pdf#page=39&selection=64,0,71,15&color=yellow|Thomas2018, p.39]]
[^2]: squaring in the formula
[^3]: [[Thomas2018.pdf#page=42&selection=172,10,173,9&color=yellow|Thomas2018, p.42]]