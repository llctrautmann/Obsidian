---
title: Supervised Learning
date: 31-05-2023
time: 14:34
author: Luca Trautmann
tags: []
series: "Machine Learning Fundamentals"
chapter: 4
---

# Supervised Learning
Supervised learning at its core is a mapping from one or more inputs to one or more outputs. There are a handful of key terms that will be defined here: 
1. _Inference_ in this context means the entire process of generating an output from an input,
2. _Parameter_ are the parts of the model that are being changed to reach the best model fit
3. _Training_ describes the process of finding the best parameters 

## Supervised Learning Overview
In its most simple form supervised learning takes an input x and applies a model to it to create an output y. 
$$y = F[x]$$
The model also has parameters $\phi$ that will need to be accounted for as well. Hence the model will schematically look like this: 
$$y = F[x,\phi]$$

> [!Key Observation]+
> The outputs are a function of the model inputs and the trained model parameter in supervised learning problems. When we talk about learning or training a model, we mean that we attempt to find parameters $ϕ$ that make sensible output predictions from the input. We learn these parameters using a training dataset of $I$ pairs of input and output examples ${x_i, y_i}$.

The mismatch between the actual observed training data and the _inference_ values is expressed with the _loss L_. This is a scalar values that expresses the degree of mismatch between the _inference_ and the actual data. In general, we want the loss to be as small as possible. Hence we are looking for the following expression: 
$$\hat{\phi} = \underset{\phi}{\operatorname{argmin}} \bigg [ L[\{x_i, y_i\},\phi] \bigg]$$
Taking the expression apart leads to the following interpretation: __In the training process we are seeking parameter $\color{orange}\hat{\phi}$ that will minimise the loss function $\color{orange}L$, which is dependent on the inputs $\color{orange}x_i$ the outputs $\color{orange}y_i$ and the parameters $\color{orange}\phi$.__ Once we have found the optimal parameter for the training set we will then apply the model to unknown data and see if the model still yields valid results, if so we can deploy it. 

# Series
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
