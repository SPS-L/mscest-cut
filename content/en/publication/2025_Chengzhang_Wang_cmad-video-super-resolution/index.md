+++
title = "CMAD: Conditional Modeling-Adapter Diffusion for Video Super-Resolution"
date = "2026-01-01"
authors = ["Chengzhang Wang", "Jiahao Nie", "Zhiwei He", "Sotirios Chatzis"]
tags = []
publication_types = [2]
publication = "Advances in Visual Computing"
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
url_source = "https://doi.org/10.1007/978-3-032-14495-9_9"
url_video = ""
url_pdf = ""
doi = "10.1007/978-3-032-14495-9_9"
math = true
highlight = true
[image]
image = ""
caption = ""
+++
Video super-resolution (VSR) aims to restore high-resolution videos from low-resolution inputs, enhancing visual quality under real-world degradation. Existing diffusion-based VSR methods often rely on specially designed network architectures or text prompts as conditional inputs, which limits their flexibility and applicability---especially in scenarios where explicit text descriptions are unavailable. To tackle this challenge, we propose a Conditional Modeling ADapter that enables zero-modification reuse of pre-trained text-to-video diffusion models for the VSR task, called CMAD. The adapter transforms low-resolution video features into pseudo-text tokens via a pre-trained Vision Transformer (ViT) and a lightweight adapter module, allowing these features to be injected as encoder hidden states, which serve as the main conditioning interface within the diffusion model. Unlike previous methods that require redesigning or retraining task-specific backbone architectures, our design enables the model to interpret video inputs directly through its original language conditioning interface---without any modification to the pre-trained diffusion network. Experiments on several VSR benchmarks, including REDS, UDM10, and VID4, demonstrate that our method achieves reconstruction performance comparable to specialized super-resolution models, without text guidance. Moreover, CMAD provides a simple and efficient solution for adapting large-scale pre-trained diffusion models to video super-resolution tasks. The source code and models will be released.
