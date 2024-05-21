---
title: Transpose Convolutions
date:
  - 14-02-2024
time: 17:16
author: Luca Trautmann
tags: 
series: Machine Learning Fundamentals
chapter: 
status: Incomplete
modified: 2024-02-14
---
# Transpose Convolutions

Standard convolutional layers allow us to halve the size of an input tensor in both dimensions (height and width), by setting strides = 2. The convolutional transpose layer uses the same principle as a standard convolutional layer (passing a filter across the image), but is different in that setting `strides = 2` doubles the size of the input tensor in both dimensions. In a convolutional transpose layer, the strides parameter determines the internal zero padding between pixels in the image, as shown in Figure 3-5. Here, a 3 × 3 × 1 filter (gray) is being passed across a 3 × 3 × 1 image (blue) with strides = 2, to produce a 6 × 6 × 1 output tensor (green).

![[ConvTrans.png]]








