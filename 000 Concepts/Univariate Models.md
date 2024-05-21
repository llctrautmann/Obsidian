---
title: Univariate Models
date: 06-02-2024
time: 23:05
author: Luca Trautmann
tags: 
series: PML
chapter: 1
modified: 2024-02-12
---

>[!Nomenclature]-
> $Pr(A)$: Probability of Event A
> $P$: Probability Mass Function
> 

# Univariate Models
## What is Probability?

There are two different interpretations of probability:
1) __The frequentist interpretation__: In this view, probabilities represent long run frequencies of events that can happen multiple times
2) __The Bayesian interpretation__:. In this view, probability is used to quantify our uncertainty or ignorance about something; hence it is fundamentally related to information rather than repeated trials.


## Types of Uncertainty
There are two fundamental types of uncertainty:
1) __epistemic uncertainty__: A simpler term for this is __model uncertainty__. It describes ignorance about the hidden processes generating the data.
2) __aleatoric uncertainty__: It describes intrinsic variability. It cannot be reduced by acquiring more data. A simpler term would be __data uncertainty__.


## Basic Rules of Univariate Probability
For more detailed information this will link to the foundations in set theory that derive the basic axioms of probability ([[Notes on Probability Theory]]).
$$
\operatorname{Pr}(A)
$$
is the probability of event $A$. 
$$
\operatorname{Pr}(\bar{A}) = 1 - \operatorname{Pr}(A)
$$
is the probability of $A$ not happening

### Conjunction and Union of Events
The conjunction of two events is the logical AND:
$$\operatorname{Pr}(A \wedge B)=\operatorname{Pr}(A,B)$$
for independent / orthogonal events, the conjunction is given by: 
$$
\operatorname{Pr}(A \wedge B ) = \operatorname{Pr}(A)\operatorname{Pr}(B)
$$
The union of two events is the logical OR:
$$
\operatorname{Pr}(A \vee B)=\operatorname{Pr}(A)+\operatorname{Pr}(B)-\operatorname{Pr}(A \wedge B)
$$
for non-mutually exclusive events and for mutually exclusive events:
$$\operatorname{Pr}(A \vee B)=\operatorname{Pr}(A)+\operatorname{Pr}(B)$$

### Conditional Probabilities, Independence, Conditional Independence 
A conditional Probability is an event $A$ that happens given that another event $B$ has happened:
$$
\operatorname{Pr}(B \mid A) \triangleq \frac{\operatorname{Pr}(A, B)}{\operatorname{Pr}(A)}
$$
This requires $Pr(A) \neq 0$.

Events $A$ and $B$ are independent or orthogonal if the

$$
\operatorname{Pr}(A, B)=\operatorname{Pr}(A) \operatorname{Pr}(B)
$$

`// FIXME: Add crosslink to correct explanation //`

Events can be conditionally independent when both $A$ and $B$ are independent in the presence of Event $C$ 
$$
\operatorname{Pr}(A, B \mid C)=\operatorname{Pr}(A \mid C) \operatorname{Pr}(B \mid C)
$$
or
$$
A \perp B \mid C
$$

## Random Variables
If the value of $X$ is unknown and/or could change, we call it a random variable or __RV__. The set of possible values, denoted $\mathbb{X}$, is known as the __sample space__ or __state space__. An event is a set of outcomes from a given sample space. More on the topic here: [[Notes on Probability Theory]]. 

### Discrete RVs
If the sample space is finite or countably infinite, the RV is discrete. In such a case, the RV has a probability assigned to each event.
$$
P(X=x)
$$

When $\mathrm{X}$ is a discrete space any probability distribution can be represented by a probability mass function that assigns a probability to each atomic element of the space, $x: X \rightarrow[0,1]$. From these atomic allocations we can reconstruct the probability of any subset $\mathrm{A} \subset \mathrm{X}$ as
$$
\operatorname{p}(A)=\sum_{\mathrm{x} \in \mathrm{A}} \operatorname{Pr}(X=x)
$$
and any expectation value as
$$
\mathbb{E}=\sum_{\mathrm{x} \in \mathrm{X}} \operatorname{Pr}(\mathrm{x}) \mathrm{f}(\mathrm{x}) .
$$

The probabilities need to sum to 1 and be non-negative and between 0 and 1. 

>[!Note]-
>Probability mass functions also have the elegant property of transforming quite naturally along a measurable transformation $\mathrm{g}: \mathrm{X} \rightarrow \mathrm{Y}$,
> $$
> \pi_*(\mathrm{y})=\sum_{\mathrm{x} \in \mathrm{g}^{-1}(\mathrm{y})} \pi(\mathrm{x}) .
> $$
> 
> This implies that the probability of a set in $\mathrm{Y}$ is given by
> $$
> \mathbb{Pr}_{\pi_*}[\mathrm{~B}]=\sum_{\mathrm{y} \in \mathrm{B}_{\mathrm{x}} \in \mathrm{g}^{-1}(\mathrm{y})} \pi(\mathrm{x}),
> $$
> while expectation values of functions on $\mathrm{Y}$ are given by
> $$
> \mathbb{E}_{\pi_*}[\mathrm{f}]=\sum_{\mathrm{x} \in \mathrm{X}} \pi(\mathrm{x}) \mathrm{f}(\mathrm{g}(\mathrm{x})) .
> $$
> 
> For a reparameterization $\mathrm{g}$ is one-to-one and $\mathrm{g}^{-1}(\mathrm{y})$ identifies a single point. Hence the pushforward probability mass function is just a relabeling of the original probability mass function, as expected.


### Continuous RVs
If $X \in \mathbb{R}$ is a real-valued quantity it is a __continuous RV__. This makes the event uncountable. However, there are a countable number of intervals which we can partition the real line into. If we associate events with X being in each one of these intervals, we can use the methods discussed above for discrete random variables. Informally speaking, we can represent the probability of X taking on a specific real value by allowing the size of the intervals to shrink to zero, as we show below.

There are two important functions with respect to CRVs:
- Cumulative Distribution Functions (CDF)
- Probability Density Function (PDF)

#### Cumulative Distribution Functions (CDF)
The CDF is defined as:
$$
P(x) \triangleq \operatorname{Pr}(X \leq x)
$$
and is basically, the sum of the area of a PDF from left to right. The probability of being in an interval is: 
$$
\operatorname{Pr}(a<X \leq b)=P(b)-P(a)
$$

#### Probability Density Function (PDF)
The PDF is the derivative of the CDF, and shows the rate of change at any point. So the PDF is:
$$
p(x) \triangleq \frac{d}{d x} P(x)
$$
This allows us to compute the probability of an event being in an interval with
$$
\operatorname{Pr}(a<X \leq b)=\int_a^b p(x) d x=P(b)-P(a)
$$
As the size of the interval gets smaller, we can write
$$
\operatorname{Pr}(x<X \leq x+d x) \approx p(x) d x
$$



### Sets of related random variables
The joint distribution between two random variables can be defined over all possible values or intervals for $X$ and $Y$ as $p(x, y)$. For PMFs this allows the creation of a table of all possible events. __Marginnalisation__ describes the process of uncovering $p(X)$ or $p(y)$ form the joint probability function. For discrete cases this is done by summation $\\sum$, for continuous cases this requires integration $\int$  . 

To understand marginalisation and conditional distributions, two rules are required: Sum Rule and Product Rule; outlined here: [[Interactions between Random Variables]], [[Combinations of Events]]. 


### Independence and conditional independence
We say $X$ and $Y$ are unconditionally independent or marginally independent, denoted $X \perp Y$, if we can represent the joint as the product of the two marginals, i.e.,
$$
X \perp Y \Longleftrightarrow p(X, Y)=p(X) p(Y)
$$

In general, we say a set of variables $X_1, \ldots, X_n$ is (mutually) independent if the joint can be written as a product of marginals for all subsets $\left\{X_1, \ldots, X_m\right\} \subseteq\left\{X_1, \ldots, X_n\right\}$ : i.e.,
$$
p\left(X_1, \ldots, X_m\right)=\prod_{i=1}^m p\left(X_i\right)
$$
Unfortunately, unconditional independence is rare, because most variables can influence most other variables.

We say $X$ and $Y$ are conditionally independent (CI) given $Z$ iff the conditional joint can be written as a product of conditional marginals:
$$
X \perp Y \mid Z \Longleftrightarrow p(X, Y \mid Z)=p(X \mid Z) p(Y \mid Z)
$$

This leads into [[Graphical Models]]. 

### Moments of a Distribution

The content is provided here: 
- [[Moments of a Distribution]],  [[Conditional Moments]]

Additional Notes:
- linearity of expectation: $\mathbb{E}[a X+b]=a \mathbb{E}[X]+b$


## Bayesian inference 
Bayes rule follows from the product rule of probability ( related notes: [[Bayes Theorem]], [[Interactions between Random Variables]], [[Combinations of Events#The Addition Law for Probabilities]].)

### Bayes Rule

> Inference = the act of passing from sample data to generalisations, usually with calculated degrees of certainty

Bayes’ rule itself is very simple: __it is just a formula for computing the probability distribution over possible values of an unknown (or hidden) quantity $H$ given some observed data $Y = y$__.

$$
p(H=h \mid Y=y)=\frac{p(H=h) p(Y=y \mid H=h)}{p(Y=y)}
$$

A detailed derivation is here: [[Bayes Theorem#Detailed Derivation for me]].
$$
\text { posterior } \propto \text { prior } \times \text { likelihood }
$$
$P(H)$ is the __prior__, and it represents __the previous knowledge we hold over the unknown data__ `// That it is the unknown data is important to note, usually we use a simple known distribution for this.`

The term $p(Y |H = h)$ represents the distribution over the possible outcomes Y we expect to see if $H = h$; this is called the observation distribution. When we evaluate this at a point corresponding to the actual observations, $y$, we get the function $p(Y = y|H = h)$, which is called the __likelihood__.

> [!GPT Answer]-
> - **Observation Distribution**: This represents the distribution of possible outcomes that you expect to see if your prior belief about the data distribution (in this case, normal distribution with parameters μ and σ) holds true.
>     
> - **Likelihood**: This quantifies how well the observed data aligns with different values of the parameters (μ and σ) under your assumed distribution. It tells you how likely it is to observe the actual data that you observed, given different parameter values.
>     
> 
> Both the observation distribution and the likelihood function are essential in Bayesian inference, where you update your beliefs about the parameters based on observed data, incorporating both your prior knowledge and the evidence provided by the data.

In simplified terms we can write: 
$$
\text { posterior } \propto \text { prior } \times \text { likelihood }
$$
with $\propto$ meaning proportional to. 

Using Bayes rule to update a distribution over unknown values of some quantity of interest, given relevant observed data, is called Bayesian inference, or posterior inference. It can also just be called probabilistic inference.