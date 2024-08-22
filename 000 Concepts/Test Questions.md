---
modified: 2024-08-22
---


Here is the Anki card formatted for the KL divergence concept:

# How does KL divergence work?

---
KL divergence, or Kullback-Leibler divergence, measures how one probability distribution diverges from a second, reference distribution. It is defined for discrete distributions as:

$$
D_{KL}(P \parallel Q)=\sum_{x} P(x) \log \frac{P(x)}{Q(x)}
$$

For continuous distributions, it is:

$$
D_{KL}(P \parallel Q)=\int P(x) \log \frac{P(x)}{Q(x)} \, dx
$$

