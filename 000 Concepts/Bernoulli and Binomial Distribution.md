---
title: Bernoulli and Binomial Distribution
date:
  - 19-06-2024
time: 19:15
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
🍙: いや
type: 
formula: $\operatorname{Ber}(y \mid \theta) \triangleq \theta^y(1-\theta)^{1-y}$
aliases:
  - binomial
modified: 2024-06-19
---
# Definition
- the bernoulli and the binomial is used to model binary events [^1]. 
$$ \large\tag{1}
Y \sim \operatorname{Ber}(\theta)
$$
$$ \large\tag{2}
\operatorname{Ber}(y \mid \theta)= \begin{cases}1-\theta & \text { if } y=0 \\ \theta & \text { if } y=1\end{cases}
$$
$$ \large\tag{3} 
\operatorname{Ber}(y \mid \theta) \triangleq \theta^y(1-\theta)^{1-y}
$$

- the binomial is an extension of the bernoulli for more than one trial [^2]. 
$$ \large\tag{4}
\operatorname{Bin}(s \mid N, \theta) \triangleq\binom{N}{s} \theta^s(1-\theta)^{N-s}
$$
where the binomial coefficent[^3] is: 
$$ \large\tag{5}
\binom{N}{k} \triangleq \frac{N!}{(N-k)!k!}
$$


# Footnotes

[^1]: [[murphy2022.pdf#page=79&selection=109,0,113,20&color=yellow|murphy2022, p.49]]
[^2]: [[murphy2022.pdf#page=80&selection=180,0,240,38&color=yellow|murphy2022, p.50]]
[^3]: [[murphy2022.pdf#page=80&selection=270,0,305,0&color=yellow|murphy2022, p.50]]