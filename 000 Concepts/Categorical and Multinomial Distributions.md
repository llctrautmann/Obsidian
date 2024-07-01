---
title: Categorical and Multinomial Distributions
date:
  - 30-06-2024
time: 13:28
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: Definition
formula: 
aliases: []
modified: 2024-07-01
---
# Categorical and Multinomial Distributions
## Categorical 
Categorical distributions generalise the [[Bernoulli and Binomial Distribution|bernoulli]] to more than two outcomes $(C>2)$ [^1]. 

The categorical distribution is a discrete probability distribution with one parameter per class:

$$\large\tag{1}
\operatorname{Cat}(y \mid \boldsymbol{\theta}) \triangleq \prod_{c=1}^C \theta_c^{\mathbb{I}(y=c)}
$$

defines the probability mass function of the categorical distribution [^2]. It simplifies to the probability $\theta_y$ of observing the outcome $y$ in the parameter vector $\boldsymbol{\theta}$. This compact form uses the product and indicator function to elegantly represent the selection of the appropriate category's probability.

## Multinomial
The categorical is a special case of the multinomial distribution [^3]. 
$$
\mathcal{M}(\boldsymbol{y} \mid N, \boldsymbol{\theta}) \triangleq\binom{N}{y_1 \ldots y_C} \prod_{c=1}^C \theta_c^{y_c}=\binom{N}{N_1 \ldots N_C} \prod_{c=1}^C \theta_c^{N_c}
$$
where $\theta_c$ is the probability that side $c$ shows up, and
$$
\binom{N}{N_1 \ldots N_C} \triangleq \frac{N!}{N_{1}!N_{2}!\cdots N_{C}!}
$$
is the multinomial coefficient, which is the number of ways to divide a set of size $N=\sum_{c=1}^C N_c$ into subsets with sizes $N_1$ up to $N_C$. If $N=1$, the multinomial distribution becomes the categorical distribution.


## Softmax function
To avoid the requirement that $f$ directly predict a probability vector, it is common to pass the output from $f$ into the softmax function also called the multinomial logit. This is defined as follows:
$$\large\tag{3}
\operatorname{softmax}(\boldsymbol{a}) \triangleq\left[\frac{e^{a_1}}{\sum_{c^{\prime}=1}^C e^{a_{c^{\prime}}}}, \ldots, \frac{e^{a_C}}{\sum_{c^{\prime}=1}^C e^{a_{c^{\prime}}}}\right]
$$

- Softmax is related to the argmax function [^4]. And it overstates large values. 
	- This happens because the exponential function grows very quickly for larger inputs. Consequently, if one element in the input vector $\mathbf{z}$ is significantly larger than the others, its exponentiated value will be much larger than those of the other elements, and thus it will dominate the sum in the denominator.

```python
from math import exp

def softmax(a: list):
	exp_values = [exp(i) for i in a]
	total = sum(exp_values)
	return [i / total for i in exp_values]

softmax([1,2,3])

>>> [0.09003057317038046, 0.24472847105479767, 0.6652409557748219]
```

### Log-sum-exp Trick
When computing normalized probabilities $p_c = \frac{e^{a_c}}{Z(\boldsymbol{a})}$ from logits $\boldsymbol{a}$, numerical issues can arise due to overflow or underflow, especially with extreme values[^5]. To avoid these issues, the log-sum-exp trick can be used:

$$
\log \sum_{c=1}^C \exp(a_c) = m + \log \sum_{c=1}^C \exp(a_c - m)
$$

Using $m = \max_c a_c$ ensures numerical stability by keeping the largest exponentiated value at zero. This trick is implemented in the lse function:

$$
\operatorname{lse}(\boldsymbol{a}) \triangleq \log \sum_{c=1}^C \exp(a_c)
$$

Probabilities can then be computed as:

$$
p(y = c \mid x) = \exp(a_c - \operatorname{lse}(\boldsymbol{a}))
$$

For efficiency and stability, the cross-entropy loss is often computed directly from logits [^6] $\boldsymbol{a}$ rather than probabilities $\boldsymbol{p}$. For binary classification, the cross-entropy loss $\mathcal{L}$ for one example is:

$$
\mathcal{L} = -\left[\mathbb{I}(y=0) \log p_0 + \mathbb{I}(y=1) \log p_1\right]
$$

where:

$$
\log p_1 = -\operatorname{lse}([0, -a]), \quad \log p_0 = -\operatorname{lse}([0, +a])
$$

# Footnotes

[^1]: [[murphy2022.pdf#page=83&selection=121,14,127,7&color=yellow|murphy2022, p.53]]
[^2]: The categorical distribution, denoted as $\operatorname{Cat}(y \mid \boldsymbol{\theta})$, describes the probability of observing outcome $y$ given a probability vector $\boldsymbol{\theta} = (\theta_1, \theta_2, \ldots, \theta_C)$, where $\sum_{c=1}^C \theta_c = 1$. It is defined as $\operatorname{Cat}(y \mid \boldsymbol{\theta}) \triangleq \prod_{c=1}^C \theta_c^{\mathbb{I}(y=c)}$, where $\mathbb{I}(y=c)$ is an indicator function that is 1 if $y=c$ and 0 otherwise leading to $\theta=1$. For example, with $\boldsymbol{\theta} = (0.2, 0.5, 0.3)$ for outcomes $A$, $B$, and $C$: $\operatorname{Cat}(A \mid \boldsymbol{\theta}) = 0.2$, $\operatorname{Cat}(B \mid \boldsymbol{\theta}) = 0.5$, and $\operatorname{Cat}(C \mid \boldsymbol{\theta}) = 0.3$, as the formula selects the probability corresponding to the observed outcome $y$ and all other categories default to 1.
[^3]: [[murphy2022.pdf#page=83&selection=295,0,298,1&color=yellow|murphy2022, p.53]]
[^4]: [[murphy2022.pdf#page=85&selection=114,0,114,78&color=yellow|murphy2022, p.55]]
[^5]: For instance, logits $\boldsymbol{a} = (1000, 1001, 1000)$ result in $Z = \infty$ due to $e^{1000}$ being too large for standard precision, while $\boldsymbol{a} = (-1000, -999, -1000)$ result in $Z = 0$ because $e^{-1000}$ is too small.
[^6]: logits are the unnormalised output vector values