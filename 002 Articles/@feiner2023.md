---
title: Propagation and Attribution of Uncertainty in Medical Imaging Pipelines
authors: Leonhard F. Feiner, Martin J. Menten, Kerstin Hammernik, Paul Hager, Wenqi Huang, Daniel Rueckert, Rickmer F. Braren, Georgios Kaissis
year: 2023
DOI: 10.1007/978-3-031-44336-7_1
tags: 
Docstring:
  - This paper introduces a method for propagating uncertainty through sequences of deep learning models in medical imaging pipelines, enabling the aggregation of uncertainty in later stages and the derivation of a joint uncertainty measure for predictions. It also allows for the separate identification of the aleatoric (data-based) uncertainty of each component in the pipeline. The method's effectiveness is demonstrated on a pipeline that reconstructs under-sampled MR images of the brain and knee, and predicts quantitative information from these images. The study quantitatively shows that the propagated uncertainty correlates with input uncertainty and analyzes the contributions of different pipeline stages to the overall uncertainty measure.
modified: 2024-04-02
---
>[!Link]+
> File: [PDF](feiner2023.pdf)
> Zotero: [Zotero](zotero://select/items/@feiner2023)

# Summary

Uncertainty estimation, which provides a means of building explainable neural networks for medical imaging applications, have mostly been studied for single deep learning models that focus on a specific task. In this paper, we propose a method to propagate uncertainty through cascades of deep learning models in medical imaging pipelines. This allows us to aggregate the uncertainty in later stages of the pipeline and to obtain a joint uncertainty measure for the predictions of later models. Additionally, we can separately report contributions of the aleatoric, data-based, uncertainty of every component in the pipeline. We demonstrate the utility of our method on a realistic imaging pipeline that reconstructs under-sampled brain and knee magnetic resonance (MR) images and subsequently predicts quantitative information from the images, such as the brain volume, or knee side or patient’s sex. We quantitatively show that the propagated uncertainty is correlated with input uncertainty and compare the proportions of contributions of pipeline stages to the joint uncertainty measure.

# Annotations  

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=2&annotation=YZIFTD2L) Bayesian methods have been developed to estimate epistemic uncertainty in machine learning models, such as Dropout during inference [7], learning weight distributions using backpropagation [4], and model ensembling [15]. ([Feiner et al., 2023, p. 2](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=2&annotation=LX8MUER5) Another approach used Monte Carlo dropout and a heteroscedastic loss to model aleatoric and epistemic uncertainty [27]. ([Feiner et al., 2023, p. 2](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=3&annotation=JMSRIVCE) None of these works use a pipeline of deep learning models or combine the predicted uncertainty of multiple models into a joint uncertainty metric. ([Feiner et al., 2023, p. 3](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=3&annotation=NG26BTLP) Our novel technique for propagation of aleatoric uncertainty can be applied to a model cascade of arbitrary length. For simplicity, we here limit the explicit presentation of our method to one upstream model g and one downstream model ([Feiner et al., 2023, p. 3](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=3&annotation=GNNZYFW6) An example of an imaging pipeline consisting of an upstream MR image reconstruction model g, and a downstream regression model f . Both models predict a measure of aleatoric uncertainty. ([Feiner et al., 2023, p. 3](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=KD24CNAX) In the following, z denotes the input data of the pipeline, x expresses the random variable of possible intermediate outputs of the upstream model, and y is a random variable of possible outputs of the entire pipeline. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=VVHTUP48) Both x and y are associated with a single data point z of the dataset, whereas p(x|z) and p(y|z) are the distributions of the random variables that are predicted by the pipeline up to a certain model stage. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=LXSPHGLL) We estimate the mean and variance of the target normal distributions using the technique by Nix et al. [21], whereas the parameters of categorical distributions are given by softmax outputs. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=NSZJ2H99) We choose the variance or entropy of y, respectively, as an uncertainty measure. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=A6M43TEI) We follow the common practice to model image uncertainty as pixel-wise variance [14], recognizing that this neglects potential higher order spatial correlations [19]. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=8EV6VHE7) As the model g uses a heteroscedastic loss for training and outputs a tuple of arrays containing the mean image E [x] and the variance image Var [x], the image x is distributed as a diagonal multivariate normal distribution over predictions. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=YTVJ3223) Next, the downstream model f processes E [x] and Var [x]. As part of our contributions, we introduce a method to aggregate the uncertainties of the upstream model g and the downstream model f to a joint uncertainty measure. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=2TBQSKJV) The joint uncertainty measure can be calculated by marginalizing the distribution of possible predictions x of the upstream model p(y|z) = ∫ p(y|x)p(x|z)dx. We approximate this integral by Monte Carlo sampling. The form of the joint uncertainty is different for regression and classification downstream tasks. ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=4&annotation=X25LMR2M) the plausible predictions y are distributed as y ∼ N (E[y], Var[y]). However, the joint variance of the pipeline is the uncertainty of the upstream model propagated through ([Feiner et al., 2023, p. 4](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=5&annotation=WLGNQZ36) the downstream model Var[xprop] and the uncertainty of the downstream model itself Var[yds]. ([Feiner et al., 2023, p. 5](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=5&annotation=E26SP6AJ) To perform variance propagation, we obtain T Monte Carlo samples (x(1), . . . , x(T )) from the distribution p(x|z). ([Feiner et al., 2023, p. 5](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=5&annotation=BGJTFMJU) We use these Monte Carlo samples to approximate the expectation of the predictive distribution using the empirical mean E[y] ≈ μˆ y and the joint variance Var[y] by the empirical variance σ2ˆ y and the empirical mean μ∆ ([Feiner et al., 2023, p. 5](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=6&annotation=MARSES9I) In all cases, the upstream task is to reconstruct MR images from undersampled k-space data. Different undersampling rates represent a varying source of aleatoric uncertainty. ([Feiner et al., 2023, p. 6](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=6&annotation=VZ2JXA4D) We demonstrate how our method propagates the uncertainty stemming from different undersampling factors to the ultimate prediction. Additionally, we show how it facilitates the attribution of the joint uncertainty to the individual models of the pipeline. ([Feiner et al., 2023, p. 6](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=6&annotation=2TNZXQVN) In addition to the reconstructed 2D MR image, the model also outputs a map of the heteroscedastic aleatoric uncertainty. ([Feiner et al., 2023, p. 6](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=7&annotation=5QC3G7UD) the pipeline calculates the parameters of a joint categorical distribution over possible predictions containing the uncertainty information. We use the fastMRI validation set containing 199 images as test set and split the original training set containing 973 images patient-wise into two parts to train the upstream and downstream model, respectively. ([Feiner et al., 2023, p. 7](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=7&annotation=MQ7GE6I5) With increasing undersampling, the uncertainty in the data increases, which is reflected in a higher estimated reconstruction uncertainty and lower structural similarity (SSIM) compared to the ground truth image that is obtained using the entire k-space data. ([Feiner et al., 2023, p. 7](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=9&annotation=3B7B3WX4) The brain volume regression model also demonstrates that both the uncertainty in the image and the propagated uncertainty in the final prediction are positively correlated with the acceleration factor ([Feiner et al., 2023, p. 9](zotero://select/library/items/DJF9TX2T))

> [Go to annotation](zotero://open-pdf/library/items/6PGLAEB2?page=9&annotation=K9P4H3HV) Our method quantifies the models’ individual contributions to the joint uncertainty and be consequently aggregates them to a joint uncertainty measure. In extensive experiments, we have shown that our method can be integrated into real-world clinical image processing pipelines. ([Feiner et al., 2023, p. 9](zotero://select/library/items/DJF9TX2T))

