---
title: Deep Learning
date: 09-02-2024
time: 12:46
author: Luca Trautmann
tags: 
series: GDL
chapter: 2
modified: 2024-02-10
status: Complete
---
# Deep Learning Basics

> Deep learning is a class of machine learning algorithms that uses multiple stacked layers of processing units to learn high-level representations from unstructured data.

## Data for Deep Learning
There are different types of data for machine learning applications. 

![[Data_structure.png]]

When our data is unstructured, individual pixels, frequencies, or characters are almost entirely uninformative. The granularity of the data combined with the high degree of spatial dependence destroys the concept of the pixel or character as an informative feature in its own right. 

Deep learning can be applied to structured data, but its real power, especially with regard to generative modeling, comes from its ability to work with unstructured data.

## Deep Neural Networks
Any system that employs many layers to learn high-level representations of the input data is also a form of deep learning (e.g., deep belief networks). Neural networks where all adjacent layers are fully connected are called multilayer perceptrons (MLPs).

![[MLP.png]]

The input (e.g., an image) is transformed by each layer in turn, until it reaches the output layer. Each unit applies a nonlinear transformation to a weighted sum of its inputs and passes the output through to the subsequent layer. The final output layer is the culmination of this process, where the single unit outputs a probability that the original input belongs to a particular category (e.g., smiling). Training the network is comprised in finding the correct weights to classify as many images correctly as possible. BackProb is used to update the weights of the network based on a loss criterion. 

## Learning High-Level Features

![[MLP_math.png]]
### Layers
_Flatten Layer_ take the input and stack the pixel values into a column that can subsequently be fed into the network as displayed above. 

The _Dense layer_ is one of the most fundamental building blocks of a neural network. It contains a given number of units that are densely connected to the previous layer that is, every unit in the layer is connected to every unit in the previous layer, through a single connection that carries a weight.

Activations are non linear functions. The activation function is critical to ensure the neural network is able to learn complex functions and doesn’t just output a linear combination of its inputs.

![[Activations.png]]

_Softmax_ wraps values into the [0,1] range and all values will sum to 1. 
$$y_i=\frac{e^{x_i}}{\sum_{j=1}^J e^{x_j}}$$

## Convolutional Neural Networks
### Convolutions
A convolution is performed by multiplying the filter pixel-wise with the portion of the image, and summing the results. The output is more positive when the portion of the image closely matches the filter and more negative when the portion of the image is the inverse of the filter.

![[Convolutions.png]]

Moving the filter, we obtain a new array that picks out a particular feature of the input, depending on the values in the filter.

### Stride
The strides parameter is the step size used by the layer to move the filters across the input. Increasing the stride therefore reduces the size of the output tensor. For example, when `strides = 2`, the height and width of the output tensor will be half the size of the input tensor. This is useful for reducing the spatial size of the tensor as it passes through the network, while increasing the number of channels.

### Padding
Padding relates to the number of 0 added around the channels of an image to keep the size of the image constant when applying convolutions. The shape of the output from a convolutional layer with `padding = "same"` is:
$$\left(\frac{\text { input height }}{\text { stride }}, \frac{\text { input width }}{\text { stride }}, filters\right)$$

![[CNN_Diagram.png]]

## Batch Norm
Exploding gradients are a problem for weights updating in deep learning models. 

### Covariance Shift
As the network trains and the weights move further away from their random initial values, the assumption that the weights will be scaled into an acceptable range can start to break down. This phenomenon is known as __covariate shift__. 

### Training using Batch Norm
During training, a batch normalisation layer calculates the mean and standard deviation of each of its input channels across the batch and normalises by subtracting the mean and dividing by the standard deviation. This brings the weights back into an acceptable range. There are then two learned parameters for each channel: 

- the scale (gamma) 
- the shift (beta).

The output is simply the normalised input, scaled by gamma and shifted by beta.

![[BatchNorm.png]]

For single image inference after training, batch norm layers also calculate a moving average. 

#### Summary
Two weights need to be learned for every channel in the preceding layer:
  - Scale (gamma)
  - Shift (beta)
  - These are the trainable parameters.

Moving average and standard deviation must be calculated for each channel:
  - They are derived from the data passing through the layer.
  - They are called non-trainable parameters.

## Dropout
Dropout layers are very simple. During training, each dropout layer chooses a random set of units from the preceding layer and sets their output to 0. This makes the model much better at generalising to unseen data, because the network has been trained to produce accurate predictions even under unfamiliar conditions, such as those caused by dropping random units.

Dropout layers are used most commonly after dense layers since these are the most prone to overfitting due to the higher number of weights, though you can also use them after conv layers.
