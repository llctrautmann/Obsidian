---
title: Sampling Methodology Summary
date: 21-07-2023
time: 14:49
author: Luca Trautmann
tags: []
---

> [!Summary]+
> Sure! Here are the main points summarized as bullet points:
> 
> - The study took place in the Ecuadorian Andean cloud forest at the Santa Lucia Cloud Forest Reserve during an 8-week field survey in June to August 2014.
> - The forest reserve is located on the western slopes of the Andes in northwestern Ecuador, spanning an elevation range of 1,400 to 2,560 meters.
> - The forest is a lower montane rainforest (cloud forest) with a humid subtropical climate and surrounded by fragmented forest reserves and cultivated pasture lands.
> - The reserve consists of different habitat types, including Ancient Primary Forest (FP), secondary regrowth (FS) areas, and silvopasture (S) used for mule grazing.
> - Acoustic data was collected using nine digital audio field recorders (Song Meter SM2+), providing three replicates of each habitat type.
> - Recording schedules covered full dawn choruses, dusk choruses, midday activity, and intermittent 3-minute recordings throughout the study period.
> - The SM2+ recorders have omni-directional microphones with a flat frequency response between 20 Hz and 20 kHz and <mark style="background: #FFB86CA6;">recorded at 16-bit with a 44.1 kHz sampling rate</mark>.
> - A local ornithologist conducted point count surveys during the dawn chorus to identify bird species and provide presence-absence and abundance measures.
> - Various acoustic indices (NDSI, H, ADI, AEI, ACI, BI) were calculated using the seewave and soundecology packages in R for dawn chorus recordings.
> - Audio spectrum approximation methods were employed, including dictionary learning, a Gabor field dictionary, and shift-invariant 2D Principle Latent Component Analysis (SI-PLCA2D).
> - A potential future direction explored the use of SI-PLCA variant (SI-PLCA2) with 2D dual dictionaries based on frequency-local time functions and frequency-shift-global time activations.
> - The study provides valuable insights into acoustic patterns and biodiversity in the Andean cloud forest, with comprehensive data on bird species vocalizations in different habitat types.
> - The use of advanced acoustic analyses and audio spectrum approximation methods offers potential for further investigations of complex soundscapes and biodiversity in the region.

# Sampling Methodology Summary
**Study Area and Data Collection:**
The study took place in the Ecuadorian Andean cloud forest at the Santa Lucia Cloud Forest Reserve (SLR) during an 8-week field survey in June to August 2014. The SLR is situated on the western slopes of the Andes in northwestern Ecuador and covers an elevation range of 1,400 to 2,560 meters. The forest is characterized as lower montane rain forest or cloud forest and is surrounded by fragmented forest reserves mixed with cultivation and pasture lands. The region is part of the Tropical Andes biodiversity hotspot, known for its high plant species endemism and diversity.

The SLR comprises a mosaic of habitat types, including Ancient Primary Forest (FP), secondary regrowth areas (FS) of around 20 years, and silvopasture (S) used as grazing paddocks for mules. These habitat types create subtle gradients in the environment, making it suitable for studying biodiversity and acoustic patterns.

**Acoustic Data Collection:**
Nine digital audio field recorders, Song Meter SM2+ (Wildlife Acoustics), were used to collect acoustic data. Three replicates of each habitat type (FP, FS, and S) were recorded, with a minimum distance of 300 meters between recorders to avoid pseudo-sampling. The recording schedules covered full dawn choruses (150 minutes), dusk choruses (90 minutes), and midday activity (60 minutes). Additionally, 3-minute recordings were taken every 15 minutes throughout the rest of the period. Each study site was recorded for a minimum of 14 days.

The SM2+ recorders are schedulable, off-line, and weatherproof, equipped with two omni-directional microphones with a flat frequency response between 20 Hz and 20 kHz. The recordings were made at 16-bit with a sampling rate of 44.1 kHz and pre-processed with a high-pass filter at 500 Hz to reduce aircraft and local generator noise.

**Species Identification:**
A local expert ornithologist conducted point count surveys during the dawn chorus. These surveys involved recording all bird species seen and heard at each survey point for 10-minute periods. The data collected from these surveys provided information on species presence-absence and abundance in the study area.

**Acoustic Indices:**
Various frequency and time domain indices were calculated using the seewave and soundecology packages in R. These indices include NDSI, H, ADI, AEI, ACI, and BI. The analysis focused on dawn chorus recordings from one day at one recording station for each habitat type (FP, FS, and S).

**Audio Spectrum Approximation Methods:**
Three different approaches to audio decomposition were demonstrated using the Bregman Media Labs Audio Patch Approximation Python package. These methods include dictionary learning using mini-batch gradient learning, a Gabor field dictionary, and shift-invariant 2D Principle Latent Component Analysis (SI-PLCA2D). Each approach uses Orthogonal Matching Pursuit (OMP) to build component reconstructions. The examples served to illustrate the potential of using a 2D atomic approach in analyzing complex quasi-periodic signals in wild soundscapes.

A potential future direction was also illustrated using a SI-PLCA variant (SI-PLCA2) that employs 2D dual dictionaries based on frequency-local time functions and frequency-shift-global time activations. The Expectation-Maximization (EM) algorithm is utilized to build component reconstructions.

**Conclusion:**
The data collected and analyzed during the field survey at the Santa Lucia Cloud Forest Reserve in Ecuador provide valuable insights into the acoustic patterns and biodiversity of the Andean cloud forest. The combination of acoustic recordings and species point count surveys offers a comprehensive understanding of the bird species present and their vocalizations in different habitat types. Furthermore, the use of various acoustic indices and audio spectrum approximation methods demonstrates the potential for advanced analyses in investigating complex soundscapes and understanding the unique biodiversity in the region.
