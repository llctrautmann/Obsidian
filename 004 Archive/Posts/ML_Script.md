---
title: Machine Learning Script
date: 2023-02-07
time: 14:02
tags: [ml]
course: thesis
status: NC
author: "Luca Trautmann"
---
# Machine Learning Script
## Introduction
There are three main branches of machine learning, supervised learning, unsupervised learning and reinforcement learning. Deep learning is a part of machine learning that uses multilayer - hence deep - neural networks to solve previously impossible to solve tasks. 
### Supervised Learning
Supervised learning map inputs to an output prediction. In each supervised learning problem there is an input vector that represent some data (i.e. images, sounds, sentences) which is then mapped to an output vector which is then converted into something meaningful for the observer (i.e. an image, sound, sentence). There are two main categories of supervised learning problems that are subdivided into more fine-grained subtypes: 
1. Regression problems provide a continuous number or numbers as output
2. Classification problems provide a class label as output. This is usually done with a vector giving the probabilities of each class as an output. 
#### Inputs in Supervised Learning Problems
The inputs in a supervised machine learning model can come in different shapes and are sometimes without an internal structure (tabular data) and sometimes with an internal structure (i.e. sound waves, or sentences in which the order of the input really matters). In addition, depending on the type of the task and input the size of the inputs may vary and become very large so the model needs to be able to accommodate inputs of very large size. 
#### Machine Learning Models
Fundamentally, a model is a set of equations that takes the input vector and returns an output vector after applying all equations to it. In machine learning the process of finding the ideal model is called _training_ and usually happens on specially assigned training data. In supervised training tasks this requires pairs of _inputs_ and _labels_ in the training data, that are being used to learn which set of equation (model) is best. 
Deep neural networks are a class of models that are suitable for very large datasets or variable data. They are able to represent a very broad family of relationships and are functional in all types of supervised learning issues. 
#### Outputs in Supervised Learning Problems
The outputs in supervised learning problems using deep learning can be as diverse as the inputs. Generally, deep learning excels in contrast to previous supervised learning methods, because it is able to retain the structure of the inputs such as the grammar of a sentence or the spatial relationship between objects in an image. 

### Unsupervised Learning
In contrast to supervised learning unsupervised learning does not rely on preexisting label pairs to work. Rather than learning a mapping from input to output, the goal is to describe or understand the structure of the data. As for supervised learning, the data may have very different characteristics; it may be discrete or continuous, low-dimensional or higher dimensional, and of constant or variable length.
#### Generative Models 
Generative unsupervised models use data to create new data that is __statistically indistinguishable__ from its training data. The methods how these models generate the data is diverse and range from _explicitly describing the input domain of the training data_ to _learning the mechanisms that generate the examples_. So far, these model excel especially in image generation, image augmentation and various text based tasks such as text completion. 
#### Latent Variables
Some (but not all) generative models exploit the observation that data can be __lower dimensional than the raw number of observed variables suggests. This leads to the idea that we can describe each data example using a smaller number of underlying latent variables.__ Here, the role of deep learning is to describe the mapping between these latent variables and the data. These __latent variables have a simple probability distribution by design.__ By sampling from this distribution and passing the result through the deep learning model, we can create new samples.
Generative models with latent variables can also benefit supervised learning models where the outputs have structure. For example, consider learning to predict the images corresponding to a caption. Rather than directly map the text input to an image, we can learn a relation between latent variables that explain the text and the latent variables that explain the image.
This has three advantages. First, we may need fewer data to learn this mapping now that the inputs and outputs are lower dimensional. Second, we are more likely to generate a plausible-looking image; any sensible values of the latent variables should produce something that looks like a plausible data example. Third, if we introduce randomness to either the mapping between the two sets of latent variables or the mapping from the latent variables to the image, then we can generate multiple images that are all described well by the caption.

---
# Chapter 2: Supervised Learning
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

#### Notes: 
__Generative vs. discriminative models:__ The models y = f[x, ϕ] in this chapter are discriminative models. These make an output prediction y from real-world measurements x. Another approach is to build a generative model x = g[y, ϕ], in which the real-world measurements x are computed as a function of the output y. The generative approach has the disadvantage that it doesn’t directly predict y. To perform inference, we must invert the generative equation as y = g −1[x, ϕ] and this may be diﬀicult. However, generative models have the advantage that we can build in prior knowledge about how the data were generated.

---
# Chapter 3: Shallow Neural Networks
Shallow neural networks are functions that map multivariate inputs $x$ to multivariate outputs $y$.   On a high level, all neural networks are __universal function approximations__ with certain level of precision (__Universal Approximation Theorem__). The more hidden activation units in the network, the closer the approximation of a continuous function is. 

## Multivariate Inputs and Outputs
The Universal Approximation Theorem also holds for multivariate inputs and outputs. In these cases, the network will map the inputs $[x_1, x_2, x_3, ... , x_N]^T$ to the multivariate output predictions $[y_1, y_2, y_3, ... ,y_n]$. The general principle is the same as for simple functions with one input and one output. In 2D any continuous function plane will be approximated with piecewise linear polygonal regions. In higher dimensions this becomes difficult to picture but the general principle still holds - __higher dimensional functions are being approximated with linear combinations of polytopes in the multidimensional input space.__

## Shallow Neural Networks: General Case
To describe a general case for shallow neural networks, it is necessary to generalise the formula for the hidden units in the networks and the combination of these hidden networks. In general, shallow neural networks take a multidimensional input space $x \in \mathbb{R}^{D_i}$ with $D_i$ being the dimension of the input to a multidimensional output $y \in \mathbb{R}^{D_o}$ with $D_o$ being the output dimensions. For the hidden unit (node) we end up with the following equation: 
$$h_d = a \left [ \theta_{d0} + \sum^{D_i}_{i=1}\theta_{di}x_i\right]$$
where $a$ is the activation function (e.g. ReLU) and $\sum^{D_i}_{i=1}\theta_{di}x_i$ is a weighted sum of the inputs and their corresponding coefficients. 

> [!Activation Function Note]-
> The activation function permits the model to describe nonlinear relations between input and the output, and as such, it must be nonlinear itself; with no activation function, or a linear activation function, the overall mapping from input to output would be restricted to be linear. With ReLU activations, the network divides the input space into convex polytopes defined by the intersections of hyperplanes computed by the “joints” in the ReLU functions. Each convex polytope contains a different linear function.
> ![[ReLu_1.png#invert]]
> ![[ReLu_2.png#invert]]

The output $y$ is then described with the following function: 
$$y= \phi_{j0} + \sum^D_{d=1} \phi_{jd}h_d$$
Here, the output $y$ is a weighted sum of the activations $h$ and a general offsetting term (bias). 
 ![[Neural_Net_Scheme.png#invert]]
---
# Chapter 4: Deep Neural Networks
Deep neural networks differ to shallow neural networks in the number of layers between the input layer and the output layer. They have in common, that they are both piecewise linear mappings from input space to output space. 
As the number of hidden units increases, shallow neural networks improve their descriptive power. Indeed, with enough hidden units, shallow networks can describe arbitrarily complex functions in high dimensions. However, it turns out that for some functions, the required number of hidden units is impractically large. Deep networks can produce many more linear regions than shallow networks for a given number of parameters. Hence, from a practical standpoint, they can be used to describe a broader family of functions.

## Hyperparameters
Hyper-parameters are fixed parameters that do not change through training. Examples are the number of nodes in each layer and the number of layers. These are predetermined before the training process takes place. For fixed hyperparameters (e.g., K = 2 layers with D k= 3 hidden units in each), the model describes a family of functions, and the parameters determine the particular function. Hence, when we also consider the hyperparameters, we can think of neural networks as representing a family of families of functions relating input to output.

## Matrix Notation in Neural Networks
Usually in Machine Learning we use Matrix Notation because it makes everything more concise and allows for easier mathematics. Complex and hierarchical equation systems such as the ones discussed above can then be abbreviated and displayed in much more compact fashion. Convoluted equation systems like these: 
Turn into nicely ordered and concise equations like these:

## General Notation
Generally, we can use the following notation for arbitrarily complex neural networks:
- the vector of hidden units at layer k is denominated as $h_k$,
- the intcercept/bias of $h_k$ is denoted as $\beta_k$
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

---
# Chapter 5: Loss Functions
Loss functions are the most important part of any machine learning model. They allow the model to mathematically calculate how well the parameters in the model are modelling the data. Without a good maximum likelihood function, it is not possible to make any good prediction. 
## Maximum Likelihood Estimation
In general, any machine learning model will not provide a direct prediction as its output. Instead, these models will provide a __prediction in the form of a conditional probability $\color{orange}P(y|x)$.__ The loss encourages each training output $y_i$ to have a high probability under the distribution $Pr(y_i|x_i)$ computed from the corresponding input $x_i$. 
### Computing Distributions over Outputs
Because models do not predict concrete solutions but probability distributions, there needs to be a translation between the data, the model and the output. To do so we use a probability distribution with parameters (parametric) that is defined over the output domain $y$ and let the model the best possible parameter given the input $x$. 
> [!Example]
> For example, suppose the prediction domain is y ∈ R. Here, we might choose the univariate normal distribution, which is defined on y ∈ R. This distribution is defined by the mean µ and variance σ 2, so θ = {µ, σ 2}. The machine learning model f[x, ϕ] might predict the mean µ, and the variance σ2 could be treated as an unknown constant.

### Maximum Likelihood Criterion
Each observed training output $y_i$ should have high probability under its corresponding distribution $Pr(y_i| \theta_i)$. The model parameter $\phi$ are then chosen in a way that will maximise the combined probability for all training examples $I$. 
$$\begin{align} \hat{\phi} &= \underset{\phi}{\operatorname{argmax}} \bigg [  \prod^I_{i=1}P(y_i|x_i) \bigg] \\
&= \underset{\phi}{\operatorname{argmax}} \bigg [  \prod^I_{i=1}P(y_i|\theta_i) \bigg ]\\
&=\underset{\phi}{\operatorname{argmax}} \bigg [  \prod^I_{i=1}P(y_i|f[x_i,\phi]) \bigg]\end{align}$$
This equation is the __Maximum Likelihood Criterion__. The MLC makes two implicit assumptions: 
1. The data distribution is identical for all examples
2. The data points are independent (problematic in many real world scenarios)

### Maximising The Log-Likelihood
The log functions is a monotonically increasing function that is being used because it scales the values of the function to better values without changing the information of the shape and it changes the product to a sum which makes the scalars in practical terms much easier to work with. Therefore we end up with the following equations: 
$$\begin{align} \hat{\phi} &= \underset{\phi}{\operatorname{argmax}} \bigg [  \prod^I_{i=1}P(y_i|f[x_i,\phi])\bigg] \\
&= \underset{\phi}{\operatorname{argmax}} \bigg [ \log \bigg [   \prod^I_{i=1}P(y_i|f[x_i,\phi])\bigg]\bigg]  \\
&=\underset{\phi}{\operatorname{argmax}} \bigg [ \sum^I_{i=1} \log \bigg [   P(y_i|f[x_i,\phi])\bigg]\bigg]\end{align}$$
Because optimisation problems are usually framed in terms of minimisation problems, the same is per convention done here. Therefore
$$\begin{align} \hat{\phi} &= \underset{\phi}{\operatorname{argmax}} \bigg [ \sum^I_{i=1} \log \bigg [   P(y_i|f[x_i,\phi])\bigg]\bigg] \\
&= \underset{\phi}{\operatorname{argmin}} \bigg [ - \sum^I_{i=1} \log \bigg [P(y_i|f[x_i,\phi])\bigg]\bigg] \\
&= \underset{\phi}{\operatorname{argmin}} \bigg[ L[\phi] \bigg]
\end{align}$$
Now, the output of the model is a distribution parameter for an output. If we want to get a point estimate we will simply calculate the maximum of the distribution (e..g. for a normal distribution this would be the equivalent to a mean). 
> [!Maximum Likelihood Cheat Sheet]-
> Recipe for constructing loss functions for training data using the maximum likelihood approach:
> 1. Choose a suitable probability distribution $P(y|\theta)$ defined over the domain of the predictions y with distribution parameters $\theta$. 
> 2. Set the machine learning model $f[x, ϕ]$ to predict one or more of these parameters, so $θ = f[x, ϕ]$ and $P(y|θ) = Pr(y|f[x, ϕ])$.
> 3. To train the model, find the network parameters $ϕ$ that minimize the negative log-likelihood loss function over the training dataset pairs $\{x_i, y_i\}$: $$\hat{\phi} = \underset{\phi}{\operatorname{argmin}}[L[\phi]] =  \underset{\phi}{\operatorname{argmin}} \bigg [− \sum^I_{i=1} log[P(y_i|f[x_i, \phi])] \bigg ]$$
> 4. To perform inference for a new test example x, return either the full distribution $P(y|f[x, ϕ])$ or the maximum of this distribution.
> Here are some recommended functions for known machine learning problems:
> ![[ML_functions.png]]
### Examples 
tbc
### Cross Entropy Loss
Cross-Entropy Loss is factually the same as the negative log-likelihood. The fundamental idea behind Cross Entropy Loss is the __minimisation of the distance between the empirical distribution of the observed data $y$ and the model distribution $P(y|\theta)$.__  This distance between the two distributions can be evaluated with the [[Kullback_Leibler_divergence]].  
> [!KL Divergence]+
> ![[KL_Divergence.mp4]]
> In mathematical notation the KL Divergence is given through the formula: 
> $$KL|q||p|= \int^{\infty}_{\infty}q(z)\log \left[q(z)\right]dz - \int^{\infty}_{\infty}q(z)\log[p(z)]dz$$


# Chapter 6: Fitting Models
## Gradient Descent
The process of training the networks is also call _learning_. The goal of all optimisation algorithms is to find the best values for the the parameters $\phi$ of the model $F$ that minimise the loss function $\operatorname{L}[\phi]$. In mathematical notation this will be written as: $$\hat{\phi}=\underset{\phi}{\operatorname{argmin}} \bigg [ \operatorname{L}[\phi] \bigg ]$$There are two steps that will occur iteratively until a solution that is satisfying has been discovered:
1. compute the derivatives (gradients) of the loss with respect to the parameters
2. adjust the parameters based on the gradients to decrease the loss $$\phi \longleftarrow \phi - \alpha \cdot \frac{\partial L}{\partial \phi}$$
The parameter α may be fixed (in which case, we call it a learning rate), or we may perform a line search where we try several values of α to find the one that most decreases the loss.
> [!important Note]
> The gradient step for any parameter is the__ sum of the loss values__ for all the training examples. 
> $$\frac{\partial L}{\partial \phi} = \frac{\partial}{\partial \phi} \sum^I_{i=1} \ell_i = \sum^I_{i=1} \frac{\partial \ell_i}{\partial \phi}$$
> It is therefore of paramount importance to update the parameter after all the included training examples have been calculated and not in between the calculations. 

## Stochastic Gradient Descent
Using gradient descent to find the global optimum of a high-dimensional loss function is challenging. Most functions are not convex and therefore getting stuck in a suboptimal minimum is a likely possibility. One of the main problems is that the final destination of a gradient descent algorithm is entirely determined by the starting point. Stochastic gradient descent (SGD) attempts to remedy this problem by adding some noise to the gradient at each step.

### Batches and Epochs
The mechanism for introducing randomness is simple. At each iteration, the algorithm chooses a random subset of the training data and computes the gradient from these examples alone (mini-batching). The batches are usually drawn from the dataset without replacement. The algorithm works through the training examples until it has used all the data, at which point it starts sampling from the full training dataset again. A single pass through the entire training dataset is referred to as an epoch.
SGD has several attractive features. First, although it adds noise to the trajectory, it still improves the fit to a subset of the data at each iteration. Hence, the updates tend to be sensible even if they are not optimal. Second, because it draws training examples without replacement and iterates through the dataset, the training examples all still contribute equally. Third, it is less computationally expensive to compute the gradient from just a subset of the training data. Fourth, it can (in principle) escape local minima. Fifth, it reduces the chances of getting stuck near saddle points; it is likely that at least some of the possible batches will have a significant gradient at any point on the loss function. Finally, there is some evidence that SGD finds parameters for neural networks that cause them to generalize well to new data in practice. In practice, SGD is often applied with a learning rate schedule. The learning rate $α$ starts at a high value and is decreased by a constant factor every N epochs.

### Momentum
### Nesterov accelerated momentum
## Adam




# Chapter 14: Unsupervised Learning
The defining characteristic of unsupervised learning models is that they are learned from a set of observed data $\{x_i\}$ without the presence of labels. They may be used to generate plausible new samples from the dataset, or to manipulate, de-noise, interpolate between, or compress examples. They can also be used to reveal the internal structure of a dataset (e.g., by dividing it into coherent clusters) or used to distinguish whether new examples belong to the same data set or are outliers.

## Taxonomy
Most unsupervised learning models define a mapping between the data $x$ and a set of unseen latent variables $z$. _Discriminative models_ map from the data $x$ to latent variables $z$. _Generative models_ map from the latent variables $z$ to the data $x$.
> [!important note]
> The latent variable attempts to capture the underlying structure of the data and is usually in a lower dimensional space when compared to the input data.  

The difference between Generative Adverserial Models and Probabilistic Generative Models lies in the usage of the latent variable. While GANs learn to generate data that is indistinguishable from the original data, probabilistic generative models learn to mimic the shape of the distribution that is provided in the data and adapt to the shape of the original data distribution. 

### What makes a Good Generative Model
A good generative model should include the following six properties if it relies on a latent variable $z$:
1) __Efficient Sampling__: Generating samples should be computationally inexpensive and should be GPU or TPU hardware accelerated
2) __High Quality Sampling__: The samples should not be distinguishable from the real data that the model was trained with 
3) __Coverage__: Samples should represent the entire training distribution. It is insufficient to only generate images that only look like small subset of the training data (i.e. mode collapse in the later chapter for GANs)
4) __Well behaving latent space__ Every latent variable $z$ should correspond to a plausible data example in the input space. Smooth changes in the latent variable should correspond to smooth changes in the input space. 
5) __Interpretable Latent Space__: Manipulating each dimension of the latent variable should lead to changes in the interpretable property of the data. For example, in a language model a change in $z$ should correspond to a change in the tone, topic, tense or verbosity
6) __Efficient Likelihood Computation__: If the model is probabilistic, we would like to calculate the the probability of new examples efficiently and accurately. 
7) 
_the rest will follow in the comming days I will get better at typing on this keyboard it is already relatively smooth so that is very good but I still have to get used to the height of the keys. everything else is very nice and fells very responsive and fresh for the fingers that are being moved over the keys. This is a very nice key board and I understand why people prefer mechanical keyboards over non mechanical ones feels like the text below you fingers is much more alive and ready and my alertness seems to be also higher than with a regular keyboard. Lets see how it will be to write longer texts with the keyboard and not only the jibberish that I am composing at the moment._



Yes, that's correct! The ELBO can be derived from Jensen's inequality applied to the logarithm function. 

Jensen's inequality states that for any convex function $f(\cdot)$ and any random variable $X$ with finite expected value, we have:

$$f(\mathbb{E}[X]) \le \mathbb{E}[f(X)]$$

If we apply this inequality to the logarithm function and use the fact that $\log(\cdot)$ is a concave function, we get:

$$\log(\mathbb{E}[X]) \ge \mathbb{E}[\log(X)]$$

where $X$ is a random variable. 

To derive the ELBO, we apply Jensen's inequality to the logarithm of the likelihood $P(\mathbf{x}|\mathbf{z})$ and obtain:

$$\log P(\mathbf{x}|\mathbf{z}) \ge \mathbb{E}_{Q(\mathbf{z})}[\log P(\mathbf{x}|\mathbf{z})]$$

where $\mathbb{E}_{Q(\mathbf{z})}$ is the expectation over the approximating distribution $Q(\mathbf{z})$. 

We can then add and subtract $\text{KL}[Q(\mathbf{z}) || P(\mathbf{z})]$ to the right-hand side of the above equation and rearrange terms to obtain the ELBO:

$$\mathcal{L}(Q) = \mathbb{E}_{Q(\mathbf{z})}[\log P(\mathbf{x}|\mathbf{z})] - \text{KL}[Q(\mathbf{z}) || P(\mathbf{z})] \ge \log P(\mathbf{x})$$

where $\mathcal{L}(Q)$ is the ELBO, $\text{KL}[Q(\mathbf{z}) || P(\mathbf{z})]$ is the KL divergence between $Q(\mathbf{z})$ and the prior $P(\mathbf{z})$, and $\log P(\mathbf{x})$ is the marginal likelihood of the data. 

By maximizing the ELBO with respect to the parameters of $Q(\mathbf{z})$, we are minimizing the upper bound on the negative log-likelihood of the data, which is equivalent to maximizing the log-likelihood.

## 2
That's a great question! The reason we multiply and divide the log-likelihood by an arbitrary probability distribution $q(\mathbf{z})$ over the latent variables is to obtain a tractable lower bound on the log-likelihood. 

We can rewrite the log-likelihood as:

$$\log P(\mathbf{x}|\boldsymbol{\phi}) = \log \int P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})d\mathbf{z}$$

where $\mathbf{z}$ are the latent variables. 

We then multiply and divide the integrand by $q(\mathbf{z})$, which gives:

$$\begin{aligned}
\log P(\mathbf{x}|\boldsymbol{\phi}) &= \log \int q(\mathbf{z}) \frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}d\mathbf{z} \\
&= \log \mathbb{E}_{q(\mathbf{z})}\left[\frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}\right]
\end{aligned}$$

where $\mathbb{E}_{q(\mathbf{z})}$ denotes the expectation with respect to the distribution $q(\mathbf{z})$. 

Now, we can apply Jensen's inequality to the logarithm of the expectation and obtain:

$$\log P(\mathbf{x}|\boldsymbol{\phi}) \ge \mathbb{E}_{q(\mathbf{z})}\left[\log \frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}\right]$$

which is the evidence lower bound (ELBO) I mentioned earlier. 

The advantage of using the ELBO is that the logarithm of the expectation is a concave function, which means that we can optimize the ELBO with respect to $q(\mathbf{z})$ using standard optimization techniques, such as gradient descent. This allows us to find a good approximation to the true posterior distribution $P(\mathbf{z}|\mathbf{x},\boldsymbol{\phi})$ even when the integral over all possible values of $\mathbf{z}$ is intractable.

## 3
Ah, I see what you're asking now! 

The reason we can multiply and divide the integrand by $q(\mathbf{z})$ is due to the following property of integration:

$$\int f(\mathbf{x})d\mathbf{x} = \int f(\mathbf{x})\frac{g(\mathbf{x})}{g(\mathbf{x})}d\mathbf{x} = \int \frac{f(\mathbf{x})}{g(\mathbf{x})}g(\mathbf{x})d\mathbf{x}$$

where $g(\mathbf{x})$ is any function that does not depend on $\mathbf{x}$ and is non-zero over the support of $f(\mathbf{x})$. 

In our case, we want to compute the log-likelihood $\log P(\mathbf{x}|\boldsymbol{\phi})$, which involves integrating over the joint distribution $P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})$. However, this integral is intractable. So, we multiply and divide the integrand by an arbitrary distribution $q(\mathbf{z})$ and use the above property of integration to obtain:

$$\begin{aligned}
\log P(\mathbf{x}|\boldsymbol{\phi}) &= \log \int q(\mathbf{z}) \frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}d\mathbf{z} \\
&= \log \int \frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}q(\mathbf{z})d\mathbf{z} \\
&= \log \mathbb{E}_{q(\mathbf{z})}\left[\frac{P(\mathbf{x},\mathbf{z}|\boldsymbol{\phi})}{q(\mathbf{z})}\right]
\end{aligned}$$

where $\mathbb{E}_{q(\mathbf{z})}$ denotes the expectation with respect to the distribution $q(\mathbf{z})$. 

This step is a common technique in variational inference and is called importance sampling. By multiplying and dividing the integrand by $q(\mathbf{z})$, we can rewrite the integral as an expectation with respect to $q(\mathbf{z})$, which is tractable. We can then use Jensen's inequality to derive a lower bound on the log-likelihood, which can be optimized using gradient-based methods to obtain an approximation to the true posterior distribution $P(\mathbf{z}|\mathbf{x},\boldsymbol{\phi})$.


The plus sign in the last step between the last two terms is because we are adding the term $\mathbb{E}_{q_\phi}[\log p_\theta(\mathbf{x})]$ to both sides of the equation. 

In the second term on the right-hand side, we can rewrite $\log \frac{p_\theta(\mathbf{z}, \mathbf{x})}{p_\theta(\mathbf{x})}$ as $\log p_\theta(\mathbf{z}, \mathbf{x}) - \log p_\theta(\mathbf{x})$. So, when we move $\mathbb{E}_{q_\phi}[\log p_\theta(\mathbf{x})]$ to the right-hand side of the equation, we get:

$$
\begin{aligned}
& =\mathbb{E}_{q_\phi}\left[\log q_\phi(\mathbf{z} \mid \mathbf{x})\right]-\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{z}, \mathbf{x})\right]+\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{x})\right] \\
& =\mathbb{E}_{q_\phi}\left[\log q_\phi(\mathbf{z} \mid \mathbf{x})\right]-\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{z}, \mathbf{x}) - \log p_\theta(\mathbf{x})\right]+\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{x})\right] \\
& =\mathbb{E}_{q_\phi}\left[\log q_\phi(\mathbf{z} \mid \mathbf{x})\right]+\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{x})\right]-\mathbb{E}_{q_\phi}\left[\log p_\theta(\mathbf{z}, \mathbf{x})\right]
\end{aligned}
$$

So, we have a plus sign between the last two terms.