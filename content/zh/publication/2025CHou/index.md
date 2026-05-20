+++
title = "Automated Prostate Segmentation in Ultrasound Images Based on Different Pre-processing Schemes"
date = "2025-01-01"
authors = ["Jiale Hou", "Huang Xiwei", "Christos P. Loizou"]
tags = ["prostate segmentation", "transrectal ultrasound imaging", "image pre-processing", "deep learning", "DeepLabv3+", "speckle noise reduction"]
publication_types = [2]
publication = "*IFIP Advances in Information and Communication Technology*"
publication_short = "IFIP AICT"
abstract = ""
summary = ""
featured = false
doi = "10.1007/978-3-031-96235-6_3"
math = true
highlight = true
[image]
image = ""
caption = ""
+++

This study proposes an automated segmentation of prostate cancer in transrectal ultrasound images using different preprocessing methods to enhance the segmentation accuracy. We propose the use of image intensity normalization and despeckle filtering, individually and in combination, as preprocessing techniques to improve the performance of a deep learning segmentation model (DeepLabv3 +) in ultrasound images of prostate cancer. This algorithm was applied to a dataset of 647 TRUS images. All images were separated into four groups as follows: original (O), intensity normalized (N), despeckled (D), and intensity normalized and despeckled (ND). Manual segmentations of the prostate were performed by an experienced radiation oncologist and compared with automated segmentations using six different evaluation metrics. Statistical analysis showed that preprocessing enhances segmentation performance, with a median (±IQR) Dice coefficient of 94.02 (3.93)/94.84 (3.92)/94.43 (3.05)/94.22 (4.19) for the O/N/D/ND images respectively. The highest segmentation accuracy was achieved on the N images, followed by the ND images which confirm the benefits of N and ND in enhancing the final segmentation accuracy. No statistically significant differences were found between all different preprocessing schemes for all the evaluation metrics investigated. Due to the small number of patients, the generalizability of the results is limited. Nevertheless, the findings highlight the potential clinical value of preprocessing in improving segmentation performance in challenging ultrasound cases. Additional experimentation with a larger image dataset and other alternative evaluation metrics is required to validate the present results.
