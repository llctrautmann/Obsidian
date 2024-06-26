---
title: Information Theory
date:
  - 21-06-2024
time: 12:01
author: Luca Trautmann
tags:
  - None
series: Information Theory
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-26
---
# Information Theory
## Entropy
- The entropy of a probability distribution can be interpreted as a measure of uncertainty, or lack of predictability, associated with a random variable drawn from a given distribution. 
- Entropy is also used to quantify information content in a data source
	- Assume: $X_{n} \sim p$ 
		- if entropy is high, it is hard to predict the value of each observation $X_{n}$. 
		- vice versa for low entropy; minimum entropy is a delta function that has all its mass in one state [^1]. 




## Entropy for discrete random variables
For a [[Random Variables|random variable]] $X$ with $K$ states, entropy is defined as:

$$ \large\tag{1}
\mathbb{H}(X) \triangleq-\sum_{k=1}^K p(X=k) \log _2 p(X=k)=-\mathbb{E}_X[\log p(X)]
$$

- usually $log_{2}$-base is used and units are called bits [^2]
- for base $e$ the units are called nats
- maximum entropy is achieved with the [[uniform distribution]]
- Estimating the entropy of a random variable with many possible states, like the identity of a word in an English document, is challenging due to the need for extensive data to account for rare and newly invented words.
	- There exist solutions but its not an easy task
\
## Cross Entropy
- Cross entropy is a measure that relates two different probability distributions
	- $\mathbb{H}_{c e}(p, q) \triangleq-\sum_{k=1}^K p_k \log q_k$
	- One can show that the cross entropy is the expected number of bits needed to compress some data samples drawn from distribution p using a code based on distribution q [^3]. 

## Joint Entropy


## Conditional Entropy


## Perplexity

$$
\text { perplexity }(p) \triangleq 2^{\mathbb{H}(p)}
$$



 
# Footnotes


[^1]: [[murphy2022.pdf#page=236&selection=139,0,140,61&color=yellow|murphy2022, p.206]]
[^2]: [[murphy2022.pdf#page=235&selection=175,4,178,1&color=yellow|murphy2022, p.205]]
[^3]: [[murphy2022.pdf#page=237&selection=251,0,259,1&color=yellow|murphy2022, p.207]]