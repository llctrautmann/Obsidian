---
title: Deep Machine Learning Introduction
date: 31-05-2023
time: 12:36
author: Luca Trautmann
tags: ["ML"]
series: "Machine Learning Fundamentals"
chapter: 0
---

# Deep Machine Learning Introduction
There are three main branches of machine learning, supervised learning, unsupervised learning and reinforcement learning. Deep learning is a part of machine learning that uses multilayer - hence deep - neural networks to solve previously impossible to solve tasks. 

## Supervised Learning
Supervised learning map inputs to an output prediction. In each supervised learning problem there is an input vector that represent some data (i.e. images, sounds, sentences) which is then mapped to an output vector which is then converted into something meaningful for the observer (i.e. an image, sound, sentence). There are two main categories of supervised learning problems that are subdivided into more fine-grained subtypes: 
1. <mark style="background: #FF5582A6;">Regression</mark> problems: provide a continuous number or numbers as output
2. <mark style="background: #FF5582A6;">Classification</mark> problems: provide a class label as output. This is usually done with a vector giving the probabilities of each class as an output. 

## Inputs in Supervised Learning Problems
The inputs in a supervised machine learning model can come in different shapes and are sometimes without an internal structure (tabular data) and sometimes with an internal structure (i.e. sound waves, or sentences in which the order of the input really matters). In addition, depending on the type of the task and input the size of the inputs may vary and become very large so the model needs to be able to accommodate inputs of very large size. 

## Machine Learning Models
<mark style="background: #FFB8EBA6;">Fundamentally, a model is a set of equations that takes the input vector and returns an output vector after applying all equations to it.</mark> In machine learning the process of finding the ideal model is called _training_ and usually happens on specially assigned training data. In supervised training tasks this requires pairs of _inputs_ and _labels_ in the training data, that are being used to learn which set of equation (model) is best. 
Deep neural networks are a class of models that are suitable for very large datasets or variable data. They are able to represent a very broad family of relationships and are functional in all types of supervised learning issues. 
### Outputs in Supervised Learning Problems
The outputs in supervised learning problems using deep learning can be as diverse as the inputs. Generally, deep learning excels in contrast to previous supervised learning methods, because it is able to retain the structure of the inputs such as the grammar of a sentence or the spatial relationship between objects in an image. 

## Unsupervised Learning
In contrast to supervised learning unsupervised learning does not rely on preexisting label pairs to work. Rather than learning a mapping from input to output, the goal is to describe or understand the structure of the data. As for supervised learning, the data may have very different characteristics; it may be discrete or continuous, low-dimensional or higher dimensional, and of constant or variable length.

### Generative Models 
Generative unsupervised models use data to create new data that is <mark style="background: #FFB8EBA6;">statistically indistinguishable from its training data</mark>. The methods how these models generate the data is diverse and range from _explicitly describing the input domain of the training data_ to _learning the mechanisms that generate the examples_. So far, these model excel especially in image generation, image augmentation and various text based tasks such as text completion. 

### Latent Variables
Some (but not all) generative models exploit the observation that data can be lower dimensional than the raw number of observed variables suggests. This leads to the idea that we can describe each data example using a smaller number of underlying latent variables. <mark style="background: #FFB8EBA6;">Here, the role of deep learning is to describe the mapping between these latent variables and the data</mark>. These latent variables have a simple probability distribution by design. By sampling from this distribution and passing the result through the deep learning model, we can create new samples.
Generative models with latent variables can also benefit supervised learning models where the outputs have structure. For example, consider learning to predict the images corresponding to a caption. Rather than directly map the text input to an image, we can learn a relation between latent variables that explain the text and the latent variables that explain the image.
This has three advantages. First, we may need fewer data to learn this mapping now that the inputs and outputs are lower dimensional. Second, we are more likely to generate a plausible-looking image; any sensible values of the latent variables should produce something that looks like a plausible data example. Third, if we introduce randomness to either the mapping between the two sets of latent variables or the mapping from the latent variables to the image, then we can generate multiple images that are all described well by the caption.

# Other Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
```
