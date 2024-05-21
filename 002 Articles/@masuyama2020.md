---
title: Phase Reconstruction Based On Recurrent Phase Unwrapping With Deep Neural Networks
authors: Yoshiki Masuyama, Kohei Yatabe, Yuma Koizumi, Yasuhiro Oikawa, Noboru Harada
year: 2020
DOI: 10.1109/ICASSP40776.2020.9053234
Tags: [ ]
Docstring: [ ]
---
>[!Link]+
> File: [PDF](masuyama2020.pdf)
> Zotero: [Zotero](zotero://select/items/@masuyama2020)

# Summary

# Annotations  

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=M3NPIQZZ) However, the training of a DNN for phase reconstruction is not an easy task because phase is sensitive to the shift of a waveform. To overcome this problem, we propose a DNN-based two-stage phase reconstruction method. In the proposed method, DNNs estimate phase derivatives instead of phase itself, which allows us to avoid the sensitivity problem. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=2CGLIJ3Y) various approaches have been studied including the consistency-based approach [11–13] and model-based approach [14]. While the former approach is based on only the property of the short-time Fourier transform (STFT) [15], the latter one explicitly uses a model of the target signal. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=25E99WKM) DNN-based phase reconstruction has the following two problems: the wrapping effect and sensitivity to a waveform shift. Since phase is wrapped in [(−π, π)], it is discontinuous at ±π even when phase rotates smoothly.([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=KVCCUL6M) mean-squared error (MSE) are not suitable for phase reconstruction because they do not take the periodic nature of phase into account. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=VFBWC9G9) Two DNNs, FIF and FGD, estimate phase derivatives. Then, phase is reconstructed by the recurrent phase unwrapping (RPU) recursively. Note that both phase derivatives are estimated from the same amplitude spectrogram, but target time-frames are different. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=MKUNSAY6) the sensitivity of phase to a waveform shift has not been considered explicitly. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=ITAPP4J5) an infinite number of Fourier phases can exist for one Fourier amplitude. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=6DK8QM7F) DNN-based direct phase estimation needs to learn an unstable map that converts a small changes in the input STFT amplitude to a large changes in the output STFT phase. ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=1&annotation=FMBNMJXP) DNNs estimate phase derivatives instead of phase itself since phase derivatives have a relation to the amplitude spectrogram [24–26]. Then, the proposed method recursively reconstructs phase from the estimated phase derivatives, which is named RPU. RPU solves a least-squares problem for estimating phase, which resembles a 2D phase unwrapping technique ([Masuyama et al., 2020, p. 1](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=6LIC7D7A) Phase is given by the complex argument of a complex-valued spectrogram, and it is wrapped in [−π, π). Hence, phase becomes discontinuous at ±π even when it rotates smoothly. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=HDJUDYKE) The second problem is the sensitivity to a shift of a waveform. Considering the Fourier transform, its amplitude is shift-invariant, i.e., the amplitude does not change by shifting a waveform. In contrast, its phase is sensitive to the shift, and thus an infinite number of Fourier phases can be considered for an amplitude spectrum. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=F85MQX8B) a DNN for direct phase estimation should learn a map reflecting small changes in amplitude spectrograms onto large differences in phases. In general, training of a DNN as such an unstable map is not an easy task. In contrast, it can be expected the estimation of phase derivatives is easier than that of phase for DNNs. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=2BSH8YT8) The von Mises distribution is a ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=594CDULV) distribution of a continuous periodic variable given by p(φ) = eκ cos(φ−μ)/2πI0(κ), where μ is a circular mean, κ is a concentration, and I0(κ) is the modified Bessel function of the first kind of order 0. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=RGBC2LND) Derived from Eq. (1), the loss function proposed in [23] is formulated by ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN)) $$\mathcal{L}(\theta)=-\sum_{\omega, \tau} \cos \left(\Phi_{\omega, \tau}^{\star}-\mathcal{F}_{\mathrm{Ph}}\left(\boldsymbol{\psi}_\tau, \theta\right)_\omega\right)$$

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=398JEGAS) This loss function is insensitive to the ambiguity of 2π of the estimated phase. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=LZAF7P3P) In the proposed method, two DNNs estimate the instantaneous frequency and group delay to avoid the sensitivity problem. Then, phase is recursively reconstructed by solving the least squares problem from its derivatives. ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=9J8JADH3) instantaneous frequency and group delay at the τ th time-frame are estimated by DNNs as follows ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN)) $$\begin{aligned}& \mathbf{v}_\tau=\mathcal{F}_{\mathrm{IF}}\left(\boldsymbol{\psi}_\tau, \theta_{\mathrm{IF}}\right) \\& \mathbf{u}_\tau=\mathcal{F}_{\mathrm{GD}}\left(\boldsymbol{\psi}_\tau, \theta_{\mathrm{GD}}\right),\end{aligned}$$

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=KGHYLEU6) DNNs are trained to minimize following loss functions: ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN)) $$  \begin{aligned}\mathcal{L}_{\mathrm{IF}}\left(\theta_{\mathrm{IF}}\right) & =-\sum_{\omega, \tau} \cos \left(V_{\omega, \tau}^{\star}-\mathcal{F}_{\mathrm{IF}}\left(\boldsymbol{\psi}_\tau, \theta_{\mathrm{IF}}\right)_\omega\right), \\\mathcal{L}_{\mathrm{GD}}\left(\theta_{\mathrm{GD}}\right) & =-\sum_{\omega, \tau} \cos \left(U_{\omega, \tau}^{\star}-\mathcal{F}_{\mathrm{GD}}\left(\boldsymbol{\psi}_\tau, \theta_{\mathrm{GD}}\right)_\omega\right),\end{aligned}$$

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=2&annotation=7BK6C7DP) Phase derivatives are treated as periodic variables because they are approximated by the difference of wrapped phase ([Masuyama et al., 2020, p. 2](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=3&annotation=F58JTSI6) The estimation of unwrapped 2D phase from its derivatives is not obvious because the unwrapped phase should be consistent in both directions. ([Masuyama et al., 2020, p. 3](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=3&annotation=9GE9EB59) The second problem is the ambiguity of the phase derivatives estimated by DNNs. The estimated instantaneous frequency and group delay have the ambiguity of 2π as discussed in the previous subsection, and we must solve this ambiguity appropriately. ([Masuyama et al., 2020, p. 3](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=3&annotation=MP5XM8DE) the appropriate group delay, which is the nearest to Dω( ˆ φτ ), is selected from the set {uω,τ ± 2nπ} by Eq. (11) as shown in the rightmost figure. ([Masuyama et al., 2020, p. 3](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=3&annotation=AWBYAP6F) Two DNNs for estimating the phase derivatives are trained by the loss functions given in Eqs. (5) and (6). Then, the proposed phase reconstruction method is summarized as follows: 1. Estimate the instantaneous frequency in the previous time-frame vτ−1 and group delay in the target time-frame uτ as in Eqs. (3) and (4), respectively. 2. Reconstruct phase by RPU: 2.1 Modify the estimated group delay as in Eqs. (10) and (11). 2.2 Estimate phase in the next time-frame by Eq. (9). 2.3 Repeat 2.1 and 2.2 for all time-frames. After reconstructing phase in all time-frames, we can obtain the complex-valued spectrogram and convert it to the time-domain. ([Masuyama et al., 2020, p. 3](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=4&annotation=UDIQRGLI) The input feature ψτ was the vector which consists of the logamplitude spectrogram at current and ±2 frames with a normalization. ([Masuyama et al., 2020, p. 4](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=4&annotation=GTSD9V82) Fully connected DNNs with 4 layers were used where each layer had 1024 units, and gated tanh nonlinearity [31] was used for the activation except the last layer. ([Masuyama et al., 2020, p. 4](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=5&annotation=UTH935MI) Phase reconstruction from amplitude spectrograms based on von–Mises-distribution deep neural network ([Masuyama et al., 2020, p. 5](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=5&annotation=NQ46E9S8) On phasemagnitude relationships in the short-time Fourier transform ([Masuyama et al., 2020, p. 5](zotero://select/library/items/VLBJ4AEN))

> [Go to annotation](zotero://open-pdf/library/items/KZLUWFDQ?page=5&annotation=TN5TWU4X) Representation of complex spectrogram via phase conversion ([Masuyama et al., 2020, p. 5](zotero://select/library/items/VLBJ4AEN))
