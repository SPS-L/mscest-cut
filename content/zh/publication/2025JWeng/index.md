+++
title = "NLMap-ATVR: A novel combination of nonlinear mapping network and adaptive total variation regularization for MRI denoising"
date = "2025-01-01"
authors = ["Yu Weng", "Zhao Jufeng", "Christakis Damianou"]
tags = ["MRI denoising", "nonlinear mapping network", "adaptive total variation regularization", "encoder-decoder network", "Bayesian optimization", "image detail preservation"]
publication_types = [1]
publication = "*Magnetic Resonance Imaging*"
publication_short = "Magn. Reson. Imaging"
abstract = ""
summary = ""
featured = false
doi = "10.1016/j.mri.2025.110608"
math = true
highlight = true
[image]
image = ""
caption = ""
+++

Magnetic resonance imaging (MRI) is an advanced imaging technique that is used to aid in medical diagnosis. However, common noises such as Gaussian and Rician noise can blur details and structures, affect contrast and reduce signal-to-noise ratio (SNR), so MRI denoising technique becomes an critical step to get noise-free MRI images. Traditional methods still have limitations in effectively balancing noise removal and the preservation of image details and structural information. To address the challenge, this paper proposes an MRI image denoising model that combines Nonlinear Mapping Network (NLMap) and Attention Mechanism-guided Adaptive Total Variation Regularization (ATVR). The model includes a NLMap-ATVR network, a crafted joint loss function and a Bayesian optimization framework. Firstly, the network uses an encoder-decoder architecture, combined with ATVR to ensure noise removal. Secondly, the joint loss function includes mean square error (MSE) loss, perceptual loss and ATVR loss, which are used to consider pixel-level and feature-level spatial structural errors to preserve details and structures. Thirdly, a Bayesian optimization framework is applied to automatically tune the hyperparameters to obtain optimal parameters. Compared with State-of-the-art methods, both subjective and objective evaluations based on experimental results demonstrate that the proposed method not only effectively removes noise but also significantly preserves details and structural information, which greatly improves SNR.
