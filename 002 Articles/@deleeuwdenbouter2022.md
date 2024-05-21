---
title: Deep learning-based single image super-resolution for low-field MR brain images
authors: M. L. De Leeuw Den Bouter, G. Ippolito, T. P. A. O’Reilly, R. F. Remis, M. B. Van Gijzen, A. G. Webb
year: 2022
DOI: 10.1038/s41598-022-10298-6
tags:
  - ML
  - Uncertainty
Docstring:
  - This work introduces a deep learning-based method that uses a convolutional neural network to enhance the resolution of images obtained from low-field MRI scanners. The network is trained using pairs of noisy low-resolution images and their corresponding noise-free high-resolution counterparts, sourced from the publicly accessible NYU fastMRI database. Once trained, the network is applied to noisy images from a low-field MRI scanner, resulting in sharp super-resolution images where most high-frequency components are recovered. This approach has the potential to significantly reduce costs and increase the accessibility of high-quality MRI technology globally, despite the traditionally lower resolution of low-field MRI scanners.
---
>[!Link]+
> File: [PDF](deleeuwdenbouter2022.pdf)
> Zotero: [Zotero](zotero://select/items/@deleeuwdenbouter2022)

# Summary


# Annotations  

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=1&annotation=F977QXIY) images acquired using low‑field MRI scanners tend to be of a relatively low resolution, as signal-to‑noise ratios are lower. ([De Leeuw Den Bouter et al., 2022, p. 1](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=1&annotation=QSWTTHXW) we present a deep learning‑based approach to transform low‑resolution low‑field MR images into high‑resolution ones. ([De Leeuw Den Bouter et al., 2022, p. 1](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=1&annotation=XSKZUPLQ) A convolutional neural network was trained to carry out single image super‑resolution reconstruction using pairs of noisy low‑resolution images and their noise‑free highresolution counterparts ([De Leeuw Den Bouter et al., 2022, p. 1](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=1&annotation=PXNW7Y4K) yielded sharp super‑resolution images in which most of the high‑frequency components were recovered. ([De Leeuw Den Bouter et al., 2022, p. 1](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=3&annotation=5A2VSZJ8) The goal of super-resolution is to find an approximate inverse of the operator  $$\mathscr{F}_{L R}^{-1} \mathbf{D} \mathscr{J}^p{ }_{H R}$$ ([De Leeuw Den Bouter et al., 2022, p. 3](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=J72ZQQ6I) SRDenseNet was introduced by Tong et al. It consists of blocks of densely connected convolutional layers (“dense blocks”). In every dense block, which is consistent with the DenseNet architecture, each convolutional layer receives as input the concatenated outputs of all preceding convolutional layers, as shown in Fig. 1. By reusing feature maps in this way the learning of redundant features is avoided. Instead, the current layer is forced to learn supplemental information. As in the original paper, we will use 8 dense blocks of 8 convolutional layers each, where each convolutional layer produces 16 feature maps, which means that each dense block yields 128 feature maps. In each convolutional layer, the kernel size is 3x3. After the final dense block, a bottleneck layer with convolutional kernels of size 1x1 is used to reduce the number of feature maps to 256, followed by a transpose convolutional layer (which is often called a deconvolution layer) which upsamples the image to HR space. ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=97HUN8JH) Finally, another convolutional layer with a 3x3 kernel is applied to reduce the output to a single channel. All layers except for the final convolutional layer use a nonlinear ReLU (Rectified Linear Unit) activation function. Additionally, skip connections are employed to feed the output of each dense block to each of the subsequent dense blocks, as is consistent with the SRDenseNet_All architecture showcased in the original paper25. ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=IJ4E7Z9E) The database consists of slices of T1-weighted, T2-weighted and FLAIR (fluid-attenuated inversion recovery) images, acquired using 1.5 T and 3 T MRI scanners. By training on such a variety of MR brain images, the resulting network should be applicable to images acquired using different sequences as well, without the need to re-train the network whenever the parameter settings change. ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=PTMGKYVF) As we are interested in HR images of 128 × 128 pixels, all images were resized to 128 × 128 pixels. This was done by using an FFT to convert the images to k-space data, selecting the central part of k-space and subsequently applying an inverse Fast Fourier Transform (FFT), as in Eq. (1). After that, we downsample these HR images to LR images of 64 × 64 pixels, by, again, using Eq. (1), i.e., we use an FFT to convert the image to k-space, select the central part of k-space (of size 64 × 64 ) and apply an inverse FFT to obtain an LR image. ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=WDFVRBA9) To obtain noisy LR images, we add complex Gaussian noise in k-space, with the noise level varying from image to image. We used a range of noise levels consistent with the low-field MR images we have seen in practice. This step is necessary to make the convolutional neural network generalize to images acquired using a low-field MRI scanner, which, due to the weaker magnetic field, yields signals with a relatively low SNR ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=5&annotation=QUZGR66I) Since SRDenseNet is a purely convolutional neural network, it is possible to train on patches instead of complete images, which requires less memory during training. Furthermore, using patches allows us to generate more data. Therefore, we used the HR-LR image pairs to create 190,000 pairs of patches to train the network on, and 10,000 pairs of patches for validation, the HR and their corresponding LR patches having a size of 32 × 32 pixels and 16 × 16 pixels, respectively. ([De Leeuw Den Bouter et al., 2022, p. 5](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=8&annotation=LKCJYJ7S) However, after visual inspection of the resulting images, we found that the mean-squared error loss outperformed the others. We used a batch size of 20 and a total number of epochs of 74 because this corresponded to the smallest value of the validation loss. ([De Leeuw Den Bouter et al., 2022, p. 8](zotero://select/library/items/TA5G2WD4))

([De Leeuw Den Bouter et al., 2022, p. 8](zotero://select/library/items/TA5G2WD4)) Blurriness in the Reconstructions is noticeable

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=8&annotation=QYLQMMDV) We pre-processed images from a publicly available dataset to obtain pairs of noisy LR images (which were meant to emulate low-field MR images as much as possible) and noise-free HR images, on which we subsequently trained the network. ([De Leeuw Den Bouter et al., 2022, p. 8](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=8&annotation=5BEAJZI7) We do note that it is of the utmost importance to be cautious when it comes to the output of neural networks. While they are very powerful, it is well known that convolutional neural network are not infallible: at times they can produce artifacts or they can fail to produce significant details. ([De Leeuw Den Bouter et al., 2022, p. 8](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=9&annotation=GDGXUW3U) acquiring enough low-field MR images to train the network from scratch is not feasible. ([De Leeuw Den Bouter et al., 2022, p. 9](zotero://select/library/items/TA5G2WD4))

> [Go to annotation](zotero://open-pdf/library/items/3GMGJT7F?page=9&annotation=B35QIUD5) The potential of deep learning-based techniques to address imaging bottlenecks in the field of low-field MRI was demonstrated by Koonjoo et al.42 They use an end-to-end deep convolutional neural network approach to boost SNR in low-field MR images acquired from highly noise-corrupted data. We note that in their paper, they describe using high-field MR data and images to train their neural network as well. ([De Leeuw Den Bouter et al., 2022, p. 9](zotero://select/library/items/TA5G2WD4))

([De Leeuw Den Bouter et al., 2022, p. 9](zotero://select/library/items/TA5G2WD4)) Is it possible to create more data by adding tiny amounts of noise to the k-space data?