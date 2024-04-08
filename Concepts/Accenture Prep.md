---
title: Accenture Prep
date:
  - 03-04-2024
time: 08:28
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-04-04
---
# Accenture Prep
# Mein Fragen
- Can you share examples of recent machine learning projects that the team has worked on? 
- What are the primary machine learning frameworks and technologies used within the team?
- How does the ML division foster innovation and stay updated with rapidly evolving ML technologies? (auch ein problem für Wissenschaftler)
- How do interns typically contribute to projects within the ML division?
- How does the ML division collaborate with other divisions within Accenture to deliver comprehensive solutions to clients?

# Wer bin ich? 
- Angehender Machine Learning Researcher im PhD program der University of Sussex
- Der Wissenschaft verschrieben
- Background in Biology, Psychology, Informatics/CS, ML
- Interessen:
	- Generative AI (Biomedical imaging)
	- Super-Resolution Model
	- Accelerated Machine Learning mit Jax, xla, flax
	- Programming: R, Python (Pytorch, bash), Rust

# ML Pipeline
1. Data Collection
2. Feature Engineering + Model Design
3. Training (train, val, test)
4. Evaluation against baseline (zero rule, random prediction, zero rule / most used class)
5. Deployment
6. Update + Maintenance 

# Wer ist Accenture
## Accenture Background
Spin out of Arthur Anderson after the Enron catastrophe. 
- started as a technology and business consulting company of Arthur Andersen, an accounting firm
-  “To help our clients create their future.”
- Genug von der Theorie? Bei uns setzt du deinen analytischen Verstand und dein kreatives Denken gezielt ein, um mit den Datenplattformen der Zukunft die Basis für Innovation und digitale Geschäftsprozesse zu bilden
- Wähle den Bereich, für den du brennst: Data Engineering, Data Science, Machine Learning, Big Data, Data Warehouse uvm.
- Du arbeitest in interdisziplinären Projektteams hautnah beim Kunden vor Ort, unterstützt bei der Modellierung komplexer Datenmodelle, konzipierst Präsentationen und Workshops und bist bei der Umsetzung live dabei

## Accenture Austria
- focus on SDG (Sustainable Development Goals)
- KI als strategischer Wachstumsmarkt
- Skalierbare KI
- Verantwortungsvoll KI

## Was ist für mich interessant
- Als Wissenschaftler habe ich eine Einsicht in experimentelle Modelle für sehr spezifische, Grundlagenforschung, die nicht unbedingt and einen Markt angepasst sein muss. Das gibt mir zwar viel Freiraum aber ich habe wenig informationen wie sich Unternehmen eine Integration von KI mit Unternehmensdaten vorstellt. 
	- Was ist möglich für Unternehmen?
	- Worauf legen Unternehmen am meisten Wert?
	- Welche Daten stehen zu Verfügung? 
	- Welche Modelle / Architectures sind für Firmen am interessantesten? 
		- Regression (Ridge, Lasso)
		- Classification
		- Clustering
		- Deep Learning (?)
		- LLMs (?)
		  Generative AI (?)
	- Inwiefern lässt sich generative AI in Unternehmensprozesse integrieren



# PyTorch

In PyTorch, the forward pass, `.backward()` method, and `.step()` method are fundamental components of the training loop for neural networks. Here's a brief description of each:

- **Forward Pass**: This is the process where the input data is passed through the neural network layer by layer from the input layer to the output layer. During the forward pass, the network makes predictions based on the current state of its weights.

- **`.backward()` Method**: After computing the loss (the difference between the predicted output and the actual output), the `.backward()` method is called on the loss tensor. This method computes the gradient of the loss function with respect to each parameter (weight) in the network by performing backpropagation. These gradients are used to adjust the weights to minimize the loss.

- **`.step()` Method**: This method is called on an optimizer object (e.g., `torch.optim.SGD`, `torch.optim.Adam`, etc.) after the gradients have been computed using `.backward()`. The `.step()` method updates the weights of the network based on the gradients computed during backpropagation. This step is what actually improves the model's predictions.

Together, these components form the core of the training loop, allowing the model to learn from the data by iteratively adjusting its weights to minimize the loss function.

## Useful Utils
**Why batchnorm?**
helps with vanishing or exploding gradients. 

**Early stopping?**
Prevents overfitting

# Frameworks
## Linear Regression
$$
y = \mathbf{x}\mathbf{w}+b
$$

loss functions: Mean Squared Error, Mean absolute error

## Logistic Regression
$$
\frac{1}{1-e^{\mathbf{x}\mathbf{w}+b}}
$$
piping the linear regression through a sigmoid function

Loss functions: Cross entropy loss (binary), Softmax (multi-classification)

$$
-\frac{1}{n} \sum_{i=1}^n\left(y_i \log \left(p_i\right)+\left(1-y_i\right) \log \left(1-p_i\right)\right)
$$

## Clustering


## Dimensionality Reduction
- PCA
- Feature Engineering

## Deep Learning
### VAE
Stochastic Autoencoder that projects the inputs onto a probability distribution. 

$$
\operatorname{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}]=\int q(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\theta}) \log [\operatorname{Pr}(\mathbf{x} \mid \mathbf{z}, \boldsymbol{\phi})] d \mathbf{z}-\mathrm{D}_{K L}[q(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\theta}) \| \operatorname{Pr}(\mathbf{z})] \text {, }
$$
which is in practice reduced to a regularised reconstruction loss:
$$
\text{reconstruction loss} + \text{kl divergence}
$$
- log variance because of numerical stability

```python
    for epoch in tqdm(range(epochs)):
        model.train()
        for idx, batch in enumerate(train_loader):
            img = batch['image'].to(device)
            
            reconstruction, mu, log_var = model(img)

            # Reconstruction loss
            reconstruction_loss = criterion(reconstruction, img)

            # KL Divergence
            kl_divergence = -0.5 * torch.sum(1 + log_var - mu.pow(2) - log_var.exp())

            # Total loss
            total_loss = reconstruction_loss + beta *  kl_divergence

            # Backprop
            optimizer.zero_grad()
            total_loss.backward()
            optimizer.step()
```

## GANs 
create a plausible data distribution by training a critic and a generator. 

issue: mode collapse

improvements: Wasserstein loss, Lipschitz Constraint

## RNNs & Autoregressive Models
Token predictors for 

## Diffusion models
Model the noise added to an image iteratively to then remove it in a reverse step to obtain a realistic image.