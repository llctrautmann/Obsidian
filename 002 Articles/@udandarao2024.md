---
title: "No “Zero-Shot” Without Exponential Data: Pretraining Concept Frequency Determines Multimodal Model Performance"
author: Vishaal Udandarao et. al.
tags: 
Docstring:
  - This research paper investigates the relationship between concept frequency in training data and the performance of multimodal models, particularly in the context of "zero-shot" generalisation. The authors analyse 34 models across 5 standard pretraining datasets, finding that model performance scales linearly with an exponential increase in concept frequency. **This log-linear scaling trend** suggests that current multimodal models exhibit significant sample inefficiency, requiring vast amounts of data to achieve performance improvements. The paper concludes that current "zero-shot" capabilities are limited and proposes the **"Let It Wag!" benchmark**, a long-tailed test set, to encourage further research into addressing these limitations.
url: 
year: 
date:
  - 09-06-2024
time: 16:03
type: Paper
modified: 2024-06-09
---
# Take-away 🥡
- Across various tasks, model types, architectures, and datasets, there is a consistent log-linear relationship between the frequency of a concept in pretraining datasets and the "zero-shot" performance of multimodal models on those concepts
## Research Ideas for Future Research
- **Investigate the causes of image-text misalignments in pretraining datasets.** For example, explore whether the methods for identifying concepts in captions and images could be improved, or if captions are often too noisy or irrelevant to the paired image.

- **Develop strategies to improve sample efficiency in multimodal models, particularly for rare concepts.** The paper found that current models require exponentially more data to improve performance on under-represented concepts. This suggests a need for new approaches to help models learn effectively from limited data.
- **Explore the impact of explicitly addressing the long-tailed distribution of concepts in pretraining datasets.** For instance, investigate whether rebalancing the data or developing new training methods could lead to better performance on under-represented concepts.
- **Further investigate the relationship between concept frequency and model performance on other downstream tasks.** The paper primarily focuses on classification, retrieval, and image generation tasks. Examining other tasks would provide a more comprehensive understanding of how concept frequency affects model capabilities.

# Annotations




> [!PDF|yellow] [[udandarao2024.pdf#page=1&selection=103,6,141,30&color=yellow|udandarao2024, p.1]]
> > CLIP is now the de-facto standard for “zero-shot” image recognition [133 , 72 , 126 , 48, 132 ] and imagetext retrieval [46 , 64 , 24, 117 , 129 ], while Stable Diffusion is now the de-facto standard for “zero-shot” text-to-image (T2I) generation

>[!PDF|red] [[udandarao2024.pdf#page=1&selection=166,17,175,81&color=red|udandarao2024, p.1]]
> > we conducted a comparative analysis involving two main factors: (1) the performance of models across various downstream tasks and (2) the frequency of test concepts within their pretraining datasets. We compiled a comprehensive list of 4, 029 concepts1 from 27 downstream tasks spanning classification, retrieval, and image generation, assessing the performance against these concepts

> [!PDF|yellow] [[udandarao2024.pdf#page=2&selection=36,0,38,99&color=yellow|udandarao2024, p.2]]
> > Our findings indicate that the impressive empirical performance of multimodal models like CLIP and Stable Diffusion can be largely attributed to the presence of test concepts within their vast pretraining datasets, thus their reported empirical performance does not constitute “zero-shot” generalization.

> [!PDF|yellow] [[udandarao2024.pdf#page=2&selection=39,16,40,77&color=yellow|udandarao2024, p.2]]
> > models require exponentially more data on a concept to linearly improve their performance on tasks pertaining to that concept, highlighting extreme sample inefficiency

> [!PDF|yellow] [[udandarao2024.pdf#page=2&selection=138,3,142,39&color=yellow|udandarao2024, p.2]]
> > Our comprehensive analysis of several pretraining image-text datasets significantly adds to this line of work, by (1) showing that concept frequency determines zero-shot performance and (2) pinpointing the exponential need for training data as a fundamental issue for current large-scale multimodal models. We conclude that the key to “zero-shot” generalization capabilities under large-scale training paradigms remains to be found.


> [!PDF|yellow] [[udandarao2024.pdf#page=6&selection=67,6,71,70&color=yellow|udandarao2024, p.6]]
> > our results clearly reveal data hungry learning, i.e, a lack in current multimodal models’ ability to learn concepts from pretraining datasets in a sample-efficient manner.

> [!PDF|yellow] [[udandarao2024.pdf#page=11&selection=248,1,259,75&color=yellow|udandarao2024, p.11]]
> > This pattern persists despite controlling for similarities between pretraining and downstream datasets or even when testing models on entirely synthetic data distributions. Further, all tested models consistently underperformed on the “Let it Wag!” dataset, which we systematically constructed from our findings to test for long-tail concepts. This underlines a critical reassessment of what “zero-shot” generalization entails for multimodal models, highlighting the limitations in their current generalization capabilities. 





