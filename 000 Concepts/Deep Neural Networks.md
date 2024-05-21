---
title: Deep Neural Networks
date: 31-05-2023
time: 14:51
author: Luca Trautmann
tags: ["ML"]
series: "Machine Learning Fundamentals"
chapter: 6
---

# Deep Neural Networks
Deep neural networks differ to shallow neural networks in the number of layers between the input layer and the output layer. They have in common, that they are both piecewise linear mappings from input space to output space. 
As the number of hidden units increases, shallow neural networks improve their descriptive power. Indeed, with enough hidden units, shallow networks can describe arbitrarily complex functions in high dimensions. However, it turns out that for some functions, the required number of hidden units is impractically large. Deep networks can produce many more linear regions than shallow networks for a given number of parameters. Hence, from a practical standpoint, they can be used to describe a broader family of functions.

## Hyperparameters
Hyper-parameters are fixed parameters that do not change through training. Examples are the number of nodes in each layer and the number of layers. These are predetermined before the training process takes place. For fixed hyper-parameters (e.g., K = 2 layers with D k= 3 hidden units in each), the model describes a family of functions, and the parameters determine the particular function. Hence, when we also consider the hyper-parameters, we can think of neural networks as representing a family of families of functions relating input to output.

## Matrix Notation in Neural Networks
Usually in Machine Learning we use Matrix Notation because it makes everything more concise and allows for easier mathematics. Complex and hierarchical equation systems such as the ones discussed above can then be abbreviated and displayed in much more compact fashion. Convoluted equation systems like these: 
Turn into nicely ordered and concise equations like these:

## General Notation
Generally, we can use the following notation for arbitrarily complex neural networks:
- the vector of hidden units at layer k is denominated as $h_k$,
- the intercept/bias of $h_k$ is denoted as $\beta_k$
- for the $k^{th}$ layer the parameters are $\Omega_k$ (e.g. $\Omega_0$ are the parameters applied to the first inputs)
- The sum of all parameters is then depicted with $\phi$ leading to $$\phi=\{\beta_k,\Omega_k\}^{K}_{k=0}$$ being the set of all parameter and with $K$ being the total number of layers in the deep neural network

## Ability Differences between Shallow and Deep Networks
Both shallow neural networks and deep neural networks are able to approximate (theoretically) any function to an arbitrary precision. However, deep neural networks are more efficient and are capable to create more linear regions for the same amount of parameters. Deep networks can create extremely large numbers of linear regions, but these contain complex dependencies and symmetries. We saw some of these when we considered deep networks as “folding” the input space. So, it’s not clear that the greater number of regions is an advantage unless (i) there are similar symmetries in the real-world functions that we wish to approximate or (ii) we have reason to believe that the mapping from input to output really does involve a composition of simpler functions.

### Depth Efficiency
Deep neural networks are much more depth efficient than shallow neural networks - meaning they are able to achieve the same level of output for less hidden nodes. While this property is very attractive, it does not hold generally for all functions and is hence dependent on the problem and the function that is being used to approximate the function. 
### Input Structure and Size
Deep neural networks have the advantage that it is possible to learn not only the best adaptation of the loss function, but also connections and dependencies in the data that are retained (e.g. objects in images are combinations of pixels that have a structural dependency on each other).

### Training and Generalisation
A further possible advantage of deep networks is ease of fitting; it is easier to train moderately deep networks than shallow ones. Deep networks also seem to generalise to new data better than shallow ones.

