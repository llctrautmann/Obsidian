---
title: Recurrent Phase Reconstruction Using Estimated Phase Derivatives from Deep Neural Networks
authors: Lars Thieling, Daniel Wilhelm, Peter Jax
year: 2021
DOI: 10.1109/ICASSP39728.2021.9413722
Tags: [ ]
Docstring: [ ]
---
>[!Link]+
> File: [PDF](thieling2021.pdf)
> Zotero: [Zotero](zotero://select/items/@thieling2021)

# Summary
# Annotations  

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=KNJZD3K3) This paper presents a deep neural network (DNN)-based system for phase reconstruction of speech signals solely from their magnitude spectrograms. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

The paper describes a novel two staged phase reconstruction algorithm based solely on the magnitude spectrogram. 

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=Q4X6MA7S) For estimating phase derivatives using DNNs, we propose 1) a new regularized cosine loss function and 2) a preprocessing step for the phase derivatives that eliminates systematic offsets in the data. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

In their work on estimating phase derivatives using deep neural networks (DNNs), Thieling et al. (2021) introduce two key contributions. Firstly, they propose a novel regularized cosine loss function. Secondly, they suggest a preprocessing step for the phase derivatives that effectively removes any systematic offsets in the data

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=TLB8L69V) Furthermore, we propose 3) a new simple but effective averaging of weighted derivative estimates for the subsequent phase reconstruction method. Experimental results confirm that the proposed reconstruction method surpasses state-of-the-art systems both in terms of the reconstructed phase spectra and the overall achieved speech quality. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

Moreover, the authors also introduce a new method for averaging weighted derivative estimates, which proves to be simple yet highly effective for the subsequent phase reconstruction process. Through experimental evaluation, it is demonstrated that this proposed reconstruction method outperforms existing systems in terms of both the reconstructed phase spectra and the overall quality of the resulting speech.

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=TXUM4975) Many audio and speech processing methods, such as speech enhancement or speech synthesis, process the time-frequency (TF) representation of signals generated via the short-time Fourier transform (STFT). ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW)) time-frequency (TF) representation = Spectrograms

Numerous techniques in audio and speech processing, such as speech enhancement or speech synthesis, operate on the time-frequency (TF) representation of signals obtained through the short-time Fourier transform (STFT). In other words, these methods work with spectrograms, which provide a visual representation of the signal's frequency content over time.

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=C5LCUYXI) This complex-valued TF representation can be divided into real-valued magnitude and phase spectra which are often used simultaneously in algorithms ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

The time-frequency (TF) representation, which consists of both magnitude and phase spectra, is a complex-valued representation commonly utilized in various algorithms. These real-valued components, namely the magnitude and phase spectra, are often employed together to enhance the performance and effectiveness of these algorithms.

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=GWFEX9BG) The former ones are usually based on the well-known Griffin-Lim algorithm [6], which fixes the magnitude spectrum and iteratively estimates the phase spectrum through STFTs and inverse STFTs by exploiting the properties of overlapping frames within the STFT calculations. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

Consistency based reconstruction models usually work based on the Griffin-Lim algorithm (GLA). GLA works by fixing the magnitude spectrum and reconstruct the phase iteratively through STFT and ISTFT exploiting certain properties in the overlapping frames within the calculations of the STFT. 

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=6NA2V5ZT) few studies that do not estimate the phase directly, but first estimate its derivatives and then reassemble them to form the most appropriate phase spectrum [12]. This two-stage system is motivated by the fact that compared to the phase, its derivatives are closer related to the magnitude spectrum [17, 18], ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=RUY2BMWM) It could be shown in [12] that the estimation of phase derivatives by time and frequency indeed shows a clear advantage compared to the direct estimation of the phase. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=XUJWTMQ5) we propose three changes to this recently introduced two-stage system [12]: 1) a new loss function, 2) a pre-processing step for the phase derivatives during training and 3) a new method for the phase reconstruction from the estimated derivatives. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=8QGTJIMR) conventional loss functions for regression problems such as the mean-squared error (MSE) loss LMSE are considered to not be suitable to estimate the phase as it is wrapped in [−π, π) and therefore is a periodic variable with a period of 2π. To overcome this ambiguity, the studies [10, 12] use the sum over the negative cosine function Lcos. This loss function was derived in [10] from a von Mises distribution of a periodic variable. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=ADS2TW8J) While LMSE has the disadvantage of discontinuity, Lcos has the disadvantage of allowing an infinite solution space, since all multiples of 2π result in the same loss. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=4UXGVGDM) Moreover, we investigate 2) a pre-processing step for the DNNs’ outputs, i.e. the phase derivatives, during training which corrects systematic shifts resulting from the discrete-time STFT (see Sec. 2.2). This procedure is referred to as shift correction (SC) ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=C9JPL2NP) Our results show that the SC of the phase derivatives in the context of phase reconstruction speeds up the training and stabilizes it w.r.t. hyperparameter variations. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=GDIX8CMD) After estimating the phase derivatives, an appropriate phase reconstruction method must be applied to ensure consistency in both directions, i.e., time and frequency. ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7088&annotation=EQRVHG8A) we propose 3) a new simple but effective method for phase reconstruction (see Sec. 2.3). The basic idea of this method is to average weighted estimates, while ([Thieling et al., 2021, p. 7088](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=XYEF62QT) taking into account the periodicity of the phase. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=HF35VNZA) Since the prediction of the phase directly suffers from a sensitivity problem w.r.t. time shifts [12] and the phase derivatives have a direct relation to the magnitude spectrum [17,18], we divide the entire phase reconstruction system into two steps. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=Q4ZFDB7F) First, the time/frequency phase derivatives are estimated using two separate DNNs. Afterwards, the phase is recursively reconstructed by applying a local averaging of estimates. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=H2LQ36PE) the phase derivatives w.r.t. time and frequency can be approximated based on the phase spectrum φ by the following differences ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=FAIMJW2I) Since the phase is a periodic variable which is wrapped to [−π, π), its derivatives also have the ambiguity of 2π. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=2AUPZ89Z) two equally structured and parameterized DNNs are simultaneously trained to minimize the following combined loss function ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=ML99MV5D) where ∆ ˆ ψif = ψif − ˆ ψif and ∆ ˆ ψgd = ψgd − ˆ ψgd are the element-wise errors of the estimated phase derivatives ˆ ψif, ˆ ψgd, respectively, and L is one out of the three loss functions shown in Fig. 2 ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=QNFXFNRV) our proposed new regularized cosine function is used for training and is given by ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW)) $$\mathcal{L}_{\text {reg }}(\Delta \hat{\psi}):=\underbrace{\sum_{k, m}-\cos (\Delta \hat{\psi}(k, m))}+\frac{(\Delta \hat{\psi}(k, m))^4}{4000}$$

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=TJ3IQW82) Furthermore, Lreg drastically reduces the allowed value range of the DNNs’ estimates (compared to Lcos) due to the additional regularization term and should therefore stabilize the training overall. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=WM78YPCT) When calculating the instantaneous frequency using (1), one can observe a systematic offset between frequency bins of consecutive time frames. This shift can be explained by the shift theorem of the discrete Fourier transform (DFT) which states that a delay in the time domain, i.e. $x(n − S)$, results in a linear phase term in the frequency domain, i.e. $X(k) · \exp(j 2π N kS)$ where S is the window shift and N is the DFT size. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=HP7R9YQ3) shift correction ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7089&annotation=UUDHYVEF) It becomes clear that by applying the shift correction the data is transformed into a new distribution, which is similar to a Gaussian distribution with a reduced standard deviation and a mean close to zero. Since the number of values near ±π is reduced, it is also less likely that an estimate near −π occurs for a label near +π during the training of the DNNs, which can lead to serious problems, e.g., if the periodicity in the loss function is neglected. ([Thieling et al., 2021, p. 7089](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7090&annotation=ZBBC5Y2V) A simple phase reconstruction could be obtained by integration along one of the estimated phase derivatives, i.e. either ˆ ψif or ˆ ψgd, as already presented in [20]. This means that for each entry in the phase spectrum the corresponding IF or GD estimation is added to the previous entry. ([Thieling et al., 2021, p. 7090](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7090&annotation=2QII4TAP) we propose a simple but effective weighted averaging of estimates that considers the periodicity of the phase. The individual estimates for averaging are determined by different paths within the TF representation which start at neighboring, already calculated phase values. Specifically, the cell entries of the estimated phase spectrum are calculated column-wise by: ([Thieling et al., 2021, p. 7090](zotero://select/library/items/4VGSNYKW)) $$\hat{\phi}(k, m)=\angle \sum_{p=1}^P \alpha_p(k, m) \cdot e^{j \varphi_p(k, m)}$$

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7090&annotation=GFAP2GZG) Then, corresponding estimated $IF_s = \hat{\phi}_{if}$ and $GD_s = \hat{\phi}_{gd}$ along the path are added or subtracted in order to estimate the target cell  $\hat{\phi}(k, m)$. ([Thieling et al., 2021, p. 7090](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7090&annotation=IHGBESNP) We have found that the estimates of phase derivatives from the DNNs tend to be less accurate for spectral components with low energy, i.e. low magnitudes, and thus the magnitude is a good estimation quality indicator. This motivated us to try different approaches for the choice of the weightings αp depending on the magnitude spectrum M . We decided to select the weight αp (k, m) as the minimum magnitude value contained in the corresponding path, i.e. α1 (k, m) = M (k − 1, m), α2 (k, m) = M (k, m − 1) and α3 (k, m) = minl={-1,0} M (k + 1, m + l). ([Thieling et al., 2021, p. 7090](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7090&annotation=WWWA7MU2) When only considering paths with small weights, i.e. αp < 0.01, the error shows larger deviations from the target value of 0 compared to the entire validation set, whereas for the paths with higher weights, i.e. αp > 0.01 and αp > 0.1, the ratio of good estimates increases. This confirms our observation that the magnitude is a good indicator for the estimation quality and demonstrates the suitability of our chosen weights. ([Thieling et al., 2021, p. 7090](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=QYF3B5TC) the proposed way of applying the shift correction in the context of phase reconstruction simplifies the entire DNN optimization procedure. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=5M8I9W6H) convergence speed for all hyperparameter configurations. On the other hand, it stabilizes the system against hyperparameter variations. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=U9UP4JQ9) we selected the best performing DNN, namely the one with LeakyReLU as activation function and Lreg as loss function, and used it to estimate the shift corrected phase derivatives ψ? if (k, m) and ψ? gd (k, m). Then, we reverted the shift correction and applied our proposed averaging method (see Sec. 2.3) to reconstruct the phase spectrum ˆ φ (k, m) again. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=F7N7BTAN) to assess the overall achieved speech quality, the original magnitude and the reconstructed phase spectra are combined and an inverse STFT is applied to obtain a time signal again. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=W54IZIMR) As can be seen from the results in Table 1, our proposed system clearly outperforms the Griffin-Lim algorithm when using 10 iterations and is only slightly worse than the Griffin-Lim with 100 iterations. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=NPMSA4IM) which makes our algorithm in principle better suited for real-time usage. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=C3T4M5N2) our algorithm could also be used to initialize the Griffin-Lim algorithm, which would significantly reduce the required iterations ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7091&annotation=RNAJKVM7) a new regularized cosine loss function and a pre-processing shift correction procedure are presented and evaluated. Both contribute to improving the DNNs’ training procedure by not only reducing the duration of training but also increasing the stability. For the second stage of phase reconstruction, we propose a new estimation averaging method which clearly outperforms a reconstruction solely from the estimated instantaneous frequency as well as the more sophisticated RPU reference algorithm. ([Thieling et al., 2021, p. 7091](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7092&annotation=HQ8BQ9AG) Phase reconstruction from amplitude spectrograms based on von-mises-distribution deep neural network ([Thieling et al., 2021, p. 7092](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7092&annotation=YRZI667H) Phase reconstruction based on recurrent phase unwrapping with deep neural networks ([Thieling et al., 2021, p. 7092](zotero://select/library/items/4VGSNYKW))

> [Go to annotation](zotero://open-pdf/library/items/SLWH4R8W?page=7092&annotation=XGZE97UD) Improving dnnbased music source separation using phase features, ([Thieling et al., 2021, p. 7092](zotero://select/library/items/4VGSNYKW))


