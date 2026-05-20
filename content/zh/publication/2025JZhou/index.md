+++
title = "Comparison of hyperbolic embedding methods for Autonomous Systems networks: machine learning versus network science"
date = "2025-01-01"
authors = ["Haojie Zhou", "Dong Zhekang", "Fragkiskos Papadopoulos"]
tags = ["hyperbolic embedding", "Autonomous Systems networks", "complex networks", "greedy routing", "link prediction", "network science"]
publication_types = [1]
publication = "*Physica Scripta*"
publication_short = "Phys. Scr."
abstract = ""
summary = ""
featured = false
doi = "10.1088/1402-4896/ae0ebe"
math = true
highlight = true
[image]
image = ""
caption = ""
+++

Hyperbolic space has emerged as a powerful framework for representing complex networks due to its ability to capture hierarchical and scale-free structures. In this work, we perform a comparative analysis of three representative hyperbolic embedding methods—Poincaré, Lorentz, and D-Mercator—on a real-world dataset: the Autonomous System (AS) Internet topology. While Poincaré and Lorentz are rooted in machine learning-based optimization, D-Mercator is derived from network science principles and provides interpretable parameters such as node popularity and similarity. We evaluate these methods using three complementary tasks: greedy routing, missing link prediction, and embedding correlation analysis. Our results show that Lorentz consistently achieves the best performance in greedy routing and ROC-based link prediction, while D-Mercator outperforms others in precision-recall evaluation. Furthermore, correlation analyses reveal strong agreement between Poincaré and Lorentz embeddings, especially for high-degree nodes, while D-Mercator produces significantly different distance structures, indicating a distinct geometric interpretation of the same network. These findings highlight the trade-offs between machine-learning-based and algorithmic hyperbolic embeddings in terms of overall accuracy, interpretability, and task-specific performance.
