+++
title = "DDPM-EMF: A Denoising Diffusion Probabilistic Model-Based Feature-Enhancement Fusion Network for Medical Image Fusion"
date = "2025-05-01"
authors = ["Yuhan Lyu", "Christakis Damianou", "Jufeng Zhao", "Guangmang Cui", "Heqing Yi", "Tianpei Zhang", "Elena Kontolemi"]
tags = []
publication_types = [1]
publication = "Journal of the Optical Society of America A, 42(5), 549-562"
publication_short = ""
abstract = ""
summary = ""
featured = false
projects = []
slides = ""
url_code = ""
url_dataset = ""
url_poster = ""
url_slides = ""
url_source = ""
url_video = ""
url_pdf = ""
doi = "10.1364/JOSAA.549576"
math = true
highlight = true
[image]
image = ""
caption = ""
+++
Medical image fusion is crucial in clinical applications, combining data from various medical imaging modalities into a single high-quality image to enhance diagnosis. However, existing fusion algorithms suffer from several limitations, including inadequate feature extraction, leading to detail loss, poor inheritance of complementary information between modalities, and insufficient evaluation of color information in color and grayscale fusion tasks. To address these challenges, we propose a novel, to our knowledge, medical image fusion framework based on the denoising diffusion probabilistic model. Our model adopts a two-stage training strategy: feature extraction and image reconstruction. An edge-enhancement dense block is designed to work with a denoising diffusion probabilistic model as a feature extractor, learning and extracting joint features from multimodal medical images to ensure comprehensive feature extraction. To further integrate meaningful information and enhance the visual quality of fused images, we design a feature-enhanced reconstruction network that amplifies features during the reconstruction process. Additionally, we develop distinct joint loss functions based on the strengths and weaknesses of different modalities, ensuring effective retention of complementary information. In the color and grayscale fusion task, we introduce a multi-channel joint learning method to ensure the retention of complementary information and incorporate a color difference formula to evaluate color retention. Experimental results demonstrate that our proposed method significantly outperforms existing state-of-the-art techniques, producing fused images with improved clarity, enhanced detail preservation, and more effective inheritance of complementary information across modalities.
