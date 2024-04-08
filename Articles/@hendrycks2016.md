---
title: Gaussian Error Linear Units (GELUs)
authors: Dan Hendrycks, Kevin Gimpel
year: 2016
DOI: 10.48550/ARXIV.1606.08415
tags:
  - ML
  - Statistics
Docstring:
  - The paper presents GELU as a sophisticated, input-dependent activation function that balances stochasticity and determinism, potentially offering enhanced capabilities in neural network modeling over existing functions like ReLU and ELU.
---
>[!Link]+
> File: [PDF](hendrycks2016.pdf)
> Zotero: [Zotero](zotero://select/items/@hendrycks2016)

# Summary
  
In the paper by Hendrycks and Gimpel (2016), the authors introduce and elaborate on the Gaussian Error Linear Unit (GELU), a novel activation function in neural networks. The GELU is contrasted with existing activation functions like ReLU and dropout. While ReLU applies a deterministic zero or one multiplication to the input, and dropout does so stochastically, GELU introduces a mechanism where this binary multiplication is both stochastic and input-dependent. This input dependency is achieved using the cumulative distribution function of the standard normal distribution.

Hendrycks and Gimpel describe GELU as scaling the input $x$ by its magnitude relative to other inputs. They present the mathematical formulation of GELU, which involves the error function, and provide simpler approximations for situations where feedforward speed is a priority over exactness. Additionally, they explore variations like the Sigmoid Linear Unit (SiLU), where different cumulative distribution functions (CDFs) are used, and discuss the absence of new hyperparameters in their experiments.

In comparison to traditional nonlinearities, GELU demonstrates superior performance across various experiments. It bears similarities to ReLU and ELU but also exhibits significant differences. For instance, GELU is non-convex and non-monotonic, showing curvature at all points, unlike ReLUs and ELUs which are linear in the positive domain and lack curvature. This increased curvature and non-monotonicity of GELU potentially allow it to approximate more complex functions than ReLUs or ELUs.

In summary, the paper presents GELU as a sophisticated, input-dependent activation function that balances stochasticity and determinism, potentially offering enhanced capabilities in neural network modeling over existing functions like ReLU and ELU.

# Annotations  

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=1&annotation=K56MIWQ5) note that a ReLU and dropout both yield a neuron’s output with the ReLU deterministically multiplying the input by zero or one and dropout stochastically multiplying by zero. ([Hendrycks and Gimpel, 2016, p. 1](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=1&annotation=FBIB9MDX) We merge this functionality by multiplying the input by zero or one, but the values of this zero-one mask are stochastically determined while also dependent upon the input. ([Hendrycks and Gimpel, 2016, p. 1](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=2&annotation=S3PHEIAC) cumulative distribution function of the standard normal distribution. ([Hendrycks and Gimpel, 2016, p. 2](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=2&annotation=4D39FDRG) In this setting, inputs have a higher probability of being “dropped” as x decreases, so the transformation applied to x is stochastic yet depends upon the input. ([Hendrycks and Gimpel, 2016, p. 2](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=2&annotation=LZPZ2L9L) Masking inputs in this fashion retains non-determinism but maintains dependency upon the input value. ([Hendrycks and Gimpel, 2016, p. 2](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=2&annotation=NDJH4E3H) we define the Gaussian Error Linear Unit (GELU) as follows:  Loosely, this expression states that we scale $x$ by how much greater it is than other inputs. Since the cumulative distribution function of a Gaussian is often computed with the error function, we define the Gaussian Error Linear Unit (GELU) as  $$\operatorname{GELU}(x)=x P(X \leq x)=x \Phi(x)=x \cdot \frac{1}{2}[1+\operatorname{erf}(x / \sqrt{2})]$$  
>   
> We can approximate the GELU with  
> $$0.5 x\left(1+\tanh \left[\sqrt{2 / \pi}\left(x+0.044715 x^3\right)\right]\right)$$  
> or  
> $$x \sigma(1.702 x)$$  
> if greater feedforward speed is worth the cost of exactness. ([Hendrycks and Gimpel, 2016, p. 2](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=2&annotation=J8PIYUSM) We could use different CDFs. For example we could use Logistic Distribution CDF σ(x) to get what we call the Sigmoid Linear Unit (SiLU) xσ(x). We could use the CDF of N (μ, σ2) and have μ and σ be learnable hyperparameters, but throughout this work we simply let μ = 0 and σ = 1. Consequently, we do not introduce any new hyperparameters in the following experiments. ([Hendrycks and Gimpel, 2016, p. 2](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=5&annotation=5P99SR8J) cross several experiments, the GELU outperformed previous nonlinearities, but it bears semblance to the ReLU and ELU in other respects. For example, as σ → 0 and if μ = 0, the GELU becomes a ReLU. More, the ReLU and GELU are equal asymptotically. In fact, the GELU can be viewed as a way to smooth a ReLU. ([Hendrycks and Gimpel, 2016, p. 5](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=6&annotation=JHNQKTVY) he GELU has several notable differences. This non-convex, non-monotonic function is not linear in the positive domain and exhibits curvature at all points. Meanwhile ReLUs and ELUs, which are convex and monotonic activations, are linear in the positive domain and thereby can lack curvature. ([Hendrycks and Gimpel, 2016, p. 6](zotero://select/library/items/KKL3Y3ZT))

> [Go to annotation](zotero://open-pdf/library/items/WADW8HB4?page=6&annotation=KBUDYQRI) ncreased curvature and non-monotonicity may allow GELUs to more easily approximate complicated functions than can ReLUs or ELUs. ([Hendrycks and Gimpel, 2016, p. 6](zotero://select/library/items/KKL3Y3ZT))



