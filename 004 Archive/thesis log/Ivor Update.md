---
title: Ivor Update
date: 07-06-2023
time: 12:28
author: Luca Trautmann
---
# Update - Luca Trautmann

## Current Progress 
I have been working mainly on the theory side of the project for the past two weeks. So far, I have reached the point at which I understand the details behind Variational Autoencoder to the point where I feel relatively confident that I could explain it to a technical audience. The biggest hurdle I had to take in the past week was understanding the following topics in depth:

- General Basics in Probability Theory, Information Theory and Deep Learning 
- Parameterisation of PDF with neural networks
- Latent Variable Models as the foundations of VAEs 
- Deriving the ELBO in all its different forms
- Variational Approximation

It has cost me some nerves to wrap my head around it, but I managed it and am confident I can start with more project-specific work in the coming days. Even though my work has been chiefly background readings and foundation, I needed to understand this before I could look further. But I have a plan for the coming weeks, and I think I am in good shape time-wise. 
## General Plan
I want to spend the remainder of June on the theory and figure out how to build the model best and what data processing I need to do. I do not want to make the mistake of just starting to code something without a real plan. For now, the following topics for me to conquer from a theoretical standpoint are the Fourier transform of the data, the components of a VAE I need to adjust, and the consequences of these adjustments on the underlying mathematics. 
## Methodology 
As mentioned above, I plan to finish the background readings and understanding of the model part in the coming week and then dive into the data and the deconstruction of the audio signals into the magnitude and phase. I have started to read the paper you suggested to me on the reconstruction of speech, and as of right now, I think I will start there with my implementation. Their model trains on the underlying data's magnitude and phase component, and I am inclined to do so as well because it would allow me to oversee my work ultimately. I am always a bit spooked at working with other people's code and would like to challenge myself and complete a project in which I could learn about both components. I do not have a complete theoretical model, but the general framework of the VAE is pretty straightforward to me. It looks like the most critical aspect of the model will be the choice of suitable distributions for both the encoder and the decoder. But I am not there yet. Similarly, I have not yet looked into the existing architectures of both neural nets. 

## Diagram 
I will, for now, stick to this overview from the paper as my baseline diagram to guide me further. 

![[model_Nugraha_et_al.png]]

I intend to initially follow their work and see how far I can get with it and then make adjustments once I encounter some trouble. On the data side, I have not looked too much into it yet, but I will do so this week. From what I can see in the paper, they use a short-time Fourier Transform to decompose the signal into the magnitude and phase component, and I think I will start there as well and then see further. 

That is it from me; I can attend the weekly meeting in person next week, so I hope I will have made more progress by then. 



