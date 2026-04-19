+++
title = "Automated Prostate Segmentation in Ultrasound Images Based on Different Pre-Processing Schemes"
date = "2025-01-01"
authors = ["Jiale Hou", "Christos P. Loizou"]
tags = []
publication_types = [2]
publication = "Proc. 21st IFIP Int. Conf. on Artificial Intelligence Applications and Innovations (AIAI 2025), IFIP AICT vol. 758, Limassol, Cyprus"
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
doi = "10.1007/978-3-031-96235-6_3"
math = true
highlight = true
[image]
image = ""
caption = ""
+++
This study presents a comprehensive framework for enhancing automated prostate segmentation in transrectal ultrasound (TRUS) images using a combination of tailored preprocessing techniques, dual-input architectures, and automated hyperparameter optimization. TRUS images are widely used in clinical practice but suffer from low contrast, speckle noise, and boundary ambiguity, which present challenges for accurate segmentation. To address these issues, this work evaluates three preprocessing schemes—intensity normalization, despeckling, and their combination—to improve input consistency and reduce imaging artifacts. Furthermore, it introduces and compares two multi-input strategies: channel expansion and a dual-branch network that separately processes normalized images and structural priors (binary or contour maps). The segmentation is performed using a modified DeepLabv3+ architecture with a MobileNetV2 backbone, and hyperparameters are optimized through a two-stage grid and Bayesian search. Experimental results on 289 TRUS images demonstrate that the dual-branch architecture, particularly the NBD strategy, achieves superior performance, with a Dice coefficient of 0.969 and strong robustness across varying conditions.
