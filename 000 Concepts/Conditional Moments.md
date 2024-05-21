---
title: Conditional Moments
date: 22-05-2023
time: 14:18
author: Luca Trautmann
tags: []
series: "Probability Theory"
chapter: 8
---

# Conditional Moments
For more than one random variables, conditional moments describe the summary statistics of one of the random variables given information on the other random variable. Conditional moments are useful in studying the relationship between two or more random variables. For example, the conditional mean or expected value of one random variable given the value of another random variable can help in predicting the behavior of the first variable based on the second variable. Similarly, the conditional variance or standard deviation of one random variable given the value of another random variable can provide insight into how much the first variable varies based on the second variable. By analyzing conditional moments, it is possible to gain a deeper understanding of the statistical properties of a system involving multiple random variables.

## Law of  Total Expectation 
The law of total expectation states mathematically the following:
$$
\mathbb{E}[X]=\mathbb{E}_Y[\mathbb{E}[X \mid Y]]
$$
The law of total expectation states that the expected value of a random variable $X$ is equal to the expected value of the conditional expected value of $X$ given another random variable $Y$. <mark style="background: #FFB86CA6;">In simpler terms, it means that the average value of X can be calculated by taking the average of X given a specific value of Y and then taking the average of all those conditional averages of X.</mark>

In practical terms this resolves itself to be the <mark style="background: #FFB8EBA6;">weighted sum of the conditional expected values given Y for discrete random variable</mark>. 
$$
\mathrm{E}[X]=\mathbf{P}\left(A_1\right) \mathrm{E}\left[X \mid A_1\right]+\cdots+\mathbf{P}\left(A_n\right) \mathrm{E}\left[X \mid A_n\right]
$$
The concept is the same for continuous random variables, but the integration does not make the "weighted sum" terminology work quite as well. 

> [!Example]+
> Assume there are two factories producing light bulbs. Let $X$ be the lifetime duration of a lightbulb, and let $Y$ be the factory the lightbulb was produced in. What is now the Expected Value of the lifetime duration $\mathbb{E}[X]$ given that we know that $\mathbb{E}[X |Y = 1] = 5000$ and  $\mathbb{E}[X |Y = 2] = 4000$ and it is known that $p(Y = 1) = 0.6$ and $p(Y = 2) = 0.4$?
> $$\mathbb{E}[X]=\mathbb{E}[X \mid Y=1] p(Y=1)+\mathbb{E}[X \mid Y=2] p(Y=2)=5000\times 0.6+4000 \times 0.4=4600$$


##  Law of Total Variance 
The law of total variance is a statistical rule that relates the total variance of a random variable to its conditional variance given another random variable. It states that the total variance of a random variable can be expressed as the sum of the conditional variance of that variable given another random variable, weighted by the probability of the other variable taking on each of its possible values. In other words, the law of total variance provides a way to decompose the total variance of a random variable into the variance that is due to the other random variable and the variance that is independent of the other random variable. The law of total variance is a useful tool in statistical analysis, as it allows researchers to better understand the sources of variance in a system involving multiple random variables.

# Chapters
```dataview
TABLE chapter as Chapter
FROM "Concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
