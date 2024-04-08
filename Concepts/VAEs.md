---
title: VAEs
date:
  - 11-02-2024
time: 16:26
author: Luca Trautmann
tags: 
series: GDL
chapter: 3
status: Incomplete
modified: 2024-02-14
---
# VAEs

In 2013, Diederik P. Kingma and Max Welling published a paper that laid the foundations for a type of neural network known as a variational autoencoder (VAE).

## Autoencoder
An autoencoder is simply a neural network that is trained to perform the task of encoding and decoding an item, such that the output from this process is as close to the original item as possible.

![[Autoencoder.png]]

The embedding space $\operatorname{z}$ (also called the __latent space__) that is the interesting part of the autoencoder, as sampling from this space will allow us to generate new images. The embedding ($\operatorname{z}$) is a compression of the original image into a lower-dimensional latent space. The idea is that by choosing any point in the latent space, we can generate novel images by passing this point through the decoder, since the decoder has learned how to convert points in the latent space into viable images

## Encoder / Decoder
This is fairly simple stuff. [[Transpose Convolutions]] for a graphic depiction of the transposed Convolution layer.

## Loss
The loss function is usually chosen to be either the root mean squared error (RMSE) or binary cross-entropy between the individual pixels of the original image and the reconstruction.

Optimising for RMSE means that your generated output will be symmetrically distributed around the average pixel values (because an overestimation is penalised equivalently to an underestimation). 

Binary cross-entropy loss is asymmetrical. It penalises errors toward the extremes more heavily than errors toward the center. For example, if the true pixel value is high (say 0.7), then generating a pixel with value 0.8 is penalised more heavily than generating a pixel with value 0.6. If the true pixel value is low (say 0.3), then generating a pixel with value 0.2 is penalised more heavily than generating a pixel with value 0.4. 

This has the effect of binary cross-entropy loss producing slightly blurrier images than RMSE loss (as it tends to push predictions toward 0.5), but sometimes this is desirable as RMSE can lead to obviously pixelised edges.

## Latent Space Properties (Autoencoder)

![[AELatentSpace.png]]

- Some clothing items are represented over a very small area and others over a much larger area.
- The distribution is not symmetrical about the point $(0,0)$, or bounded. For example, there are far more points with positive $y$-axis values than negative, and some points even extend to a $y$-axis value $>8$.
- There are large gaps between colours containing few points.

![[AELatentSpaceOverlay.png]]

This latent space leads to some interesting observations:
1) if we pick points uniformly in a bounded space that we define, we’re more likely to sample something that decodes to look like a bag
2) it is not obvious how we should go about choosing a random point in the latent space, since the distribution of these points is undefined.
3) There are holes in the embeddings. The autoencoder has no reason to ensure that points here are decoded to recognisable clothing items as very few images in the training set are encoded here. Even points that are central may not be decoded into well-formed images. This is because the autoencoder is not forced to ensure that the space is continuous. This problem become a lot more significant in higher dimensional spaces necessary for detailed reconstructions. 

## Variational Autoencoder
In an autoencoder, each image is mapped directly to one point in the latent space. In a variational autoencoder, each image is instead mapped to a multivariate normal distribution around a point in the latent space. 

![[VAEEmbeddings.png]]

### Multivariate Gaussian Distribution
The concept of a normal distribution extends to more than one dimension-the probability density function for a multivariate normal distribution (or multivariate Gaussian distribution) $\mathscr{N}(\mu, \Sigma)$ in $k$ dimensions with mean vector $\mu$ and symmetric covariance matrix $\Sigma$ is as follows:
$$
f\left(x_1, \ldots, x_k\right)=\frac{\exp \left(-\frac{1}{2}(\mathbf{x}-\mu)^{\mathrm{T}} \Sigma^{-1}(\mathbf{x}-\mu)\right)}{\sqrt{(2 \pi)^k|\Sigma|}}
$$

In this book, we will typically be using

isotropic multivariate normal distributions, 
`// An isotropic gaussian is one where the covariance matrix is represented by the simplified matrix `$\Sigma=\sigma^2 \underline{I}$`This is done to reduce computational expensive overhang incalculating the covariance matrix: see: https://math.stackexchange.com/a/2137851.`
where the covariance matrix is diagonal. This means that the distribution is independent in each dimension (i.e., we can sample a vector where each element is normally distributed with independent mean and variance). This is the case for the multivariate normal distribution that we will use in our variational autoencoder.

A multivariate standard normal distribution $\mathscr{N}(0, \mathbf{I})$ is a multivariate distribution with a zero-valued mean vector and identity covariance matrix. `Variational autoencoders assume that there is no correlation between dimensions in the latent space. 

<mark class="hltr-red">Note</mark>: We use the log variance to allow the mapping to be from $\infty$ to $-\infty$. 

![[VAE_schema.png]]

The advantage in comparison to the Autoencoder is that the model now needs to embed the values around the mean vector and hence we prevent holes. Our new samples are therefore more likely to be well-formed. 

## Reparameterisation Trick
Rather than sample directly from a normal distribution with parameters z_mean and z_log_var, we can sample epsilon from a standard normal and then manually adjust the sample to have the correct mean and variance.

This is known as the reparameterisation trick, and it's important as it means gradients can back-propagate freely through the layer. By keeping all of the randomness of the layer contained within the variable epsilon, the partial derivative of the layer output with respect to its input can be shown to be deterministic (i.e., independent of the random epsilon), which is essential for back-propagation through the layer to be possible.

## VAE Loss and [[Kullback-Leibler (KL) divergence]]
KL divergence is a way of measuring how much one probability distribution differs from another. In a VAE, we want to measure how much our normal distribution with parameters `z_mean` and `z_log_var` differs from a standard normal distribution. 

Code
```python
kl_loss = -0.5 * torch.sum(1 + z_log_var - z_mean ** 2 - torch.exp(z_log_var))`
```

Math:
$$
D_{K L}\left[N(\mu, \sigma \| N(0,1)\right]=-\frac{1}{2} \sum\left(1+\log \left(\sigma^2\right)-\mu^2-\sigma^2\right).
$$
