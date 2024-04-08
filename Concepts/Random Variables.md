---
title: Random Variables
date: 19-05-2023
time: 16:55
author: Luca Trautmann
tags: ["Mathematics"]
series: "Probability Theory"
chapter: 2
---
> [!Summary]+
> A random variable is a mathematical concept used in probability theory and statistics to represent the outcomes of a random process or experiment. It is a variable whose value is determined by chance, and can take on a range of possible values with different probabilities.

A random variable is a mathematical concept used in probability theory and statistics to represent the outcomes of a random process or experiment. It is a variable whose value is determined by chance, and can take on a range of possible values with different probabilities. Random variables can be discrete or continuous, depending on whether their possible values are countable or uncountable. 

They are used to model real-world phenomena such as the outcomes of dice rolls, the heights of individuals in a population, or the number of customers in a store. Random variables are fundamental to statistical modeling and inference, and are used to calculate probabilities, expected values, and other statistical measures that describe and predict the behavior of a random process or experiment.

For example $x = 7$ is not a random variable. However, the outcome of a dice roll is a random variable (i.e. it contains randomness and is not fixed). All the possible outcomes of the random variable are called the sample space. A random variable can take any value in the sample space. All the possibilites in the sample space are events (e.g. for a dice roll, the dice can land in 6 positions, hence there are six events):
$$S = \{1,2,3,4,5,6\}$$
Each event in the sample space have an associated probability. For example with an unbiased dice the probability for throwing a 1 is:
$$P(X= 1) = \frac{1}{6}$$
## Discrete Random Variables
If the sample space is finite or countable, then $X$ is called a __<mark style="background: #FFB8EBA6;">discrete random variable</mark>__. The event $x$ and its corresponding probability are defined as:
$$P(X=x) = \text{value}$$
The probability mass function is a mapping from the possible values of the random variable to its probabilities.
$$p(x) = P(X=x)$$

### Example: Simple PMF
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Column

#-----------------#
#- chart data    -#
#-----------------#
data:
  - label: "0"
    value: 0.3
  - label: "1"
    value: 0.3
  - label: "2"
    value: 0.4

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: label
  yField: value
```

For the PMF to be valid, two conditions need to be fulfilled. 
1. Any probability has to be between 0 and 1; hence $0 < P(X = x) < 1$
2. All probabilities have to add up to 1; hence $\sum_{i=1}^{X} = 1$


## Continuous Random Variable
If the sample space is not finite and countable the random variable will be continuous it will be called a <mark style="background: #FFB8EBA6;">continuous random variable</mark>. This will change the calculations from summations ($\sum$) to integration under the curve ($\int$) to get the corresponding probabilities.

Instead of singular events having occurring with a probability, intervals over ranges of values determine the probability. The probability for a specific value to occur is always 0.

Probability distributions for continuous random variables are described using probability density functions (PDFs, [[Density Functions]]), which represent the likelihood of a variable taking on a specific value. The area under the PDF curve represents the probability of the variable being within a certain range of values.

## Code
For an interactive notebook open:
```shell
open -a Visual\ Studio\ Code /Users/luca/Desktop/ML/ScriptsML/notebooks/Random_Variable.ipynb
