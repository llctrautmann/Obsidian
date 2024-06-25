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
modified: 2024-06-25
---
# Information Theory
## Entropy
- The entropy of a probability distribution can be interpreted as a measure of uncertainty, or lack of predictability, associated with a random variable drawn from a given distribution. 
- Entropy is also used to quantify information content in a data source
	- Assume: $X_{n} \sim p$ 
		- if entropy is high, it is hard to predict the value of each observation $X_{n}$. 
		- vice versa for low entropy; minimum entropy is a delta function that has all its mass in one state [^1]. 




## Entropy for discrete random variables

$$ \large\tag{1}
\mathbb{H}(X) \triangleq-\sum_{k=1}^K p(X=k) \log _2 p(X=k)=-\mathbb{E}_X[\log p(X)]
$$
# Footnotes

[^1]: [[murphy2022.pdf#page=236&selection=139,0,140,61&color=yellow|murphy2022, p.206]]