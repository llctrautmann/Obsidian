---
title: Expected Values and Latent Variable Models
date: 12-06-2023
time: 06:12
author: Luca Trautmann
tags: ["ML","VAE"]
series: "Probability Theory"
chapter: 11
---

# Expected Values and Latent Variable Models
In probability theory, the expected value of a random variable is a measure of its central tendency. It represents the average value that the random variable is expected to take over a large number of trials or experiments. In this post, we'll explore how expected values are related to probability distributions and how they can be calculated using integrals.

Let's start with the following equation:

$$P(x) = \int P(x,z) dz$$

The left-hand side of the equation represents the probability of observing the value x. The right-hand side of the equation is a sum over all possible values of z, where z represents some other random variable that affects the probability of observing x. 

Calculating the Expected Value

Now, let's rewrite the equation as:

$$P(x) = \int P(z) P(x|z) dz$$

If we think of P(z) as a weighting function for P(x|z), then the right-hand side of the equation becomes a weighted average of P(x|z) over all possible values of z. 

This weighted average is exactly equivalent to the definition of the expected value of P(x|z), where the weights are given by the probability distribution of z:

$$\mathbb{E}[P(x|z)] = \int P(x|z) P(z) dz$$

Therefore, we can rewrite the equation as:

$$P(x) = \int P(x|z)P(z)dz = \mathbb{E}[P(x|z)]$$

So, the probability of observing x is equal to the expected value of P(x|z), where the expectation is taken over the probability distribution of z.

Conclusion

In summary, the expected value of a random variable is a measure of its central tendency and represents the average value that the variable is expected to take over a large number of trials or experiments. Expected values can be calculated using integrals, and they are related to probability distributions through the concept of weighted averages. The equation $P(x) = \int P(x|z)P(z)dz = E[P(x|z)]$ shows that the probability of observing x is equal to the expected value of P(x|z), where the expectation is taken over the probability distribution of z.










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```