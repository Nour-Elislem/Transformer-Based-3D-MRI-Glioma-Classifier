# Transformer-Based-3D-MRI-Glioma-Classifier
In this repository, we propose a fully Transformer‑based pipeline for the early detection and grading of gliomas from 3D MRI scans, with a downstream SVM classifier for final tumor‑grade assignment. After standard preprocessing (skull‑stripping, intensity normalization, and spatial registration), volumetric patches are extracted and embedded into a sequence of tokens. A multi‑scale Transformer encoder—with 3D positional embeddings and multi‑head self‑attention—learns contextual representations across the entire brain volume, capturing both local textural variations and long‑range anatomical dependencies.

From the Transformer’s final hidden states, we automatically derive quantitative feature vectors that characterize tumor heterogeneity (e.g., attention‑weighted regional intensity distributions, shape descriptors, and attention‑guided uncertainty estimates). Those feature vectors are then fed into a Support Vector Machine, optimized via grid search on radial‑basis kernels, to distinguish Low‑Grade Gliomas (LGG) from High‑Grade Gliomas (HGG).
This repository contains three main Jupyter notebooks:

- **model-final.ipynb**  
  End‑to‑end training of our core Transformer model on preprocessed 3D MRI volumes.

- **classification_SU.ipynb**  
  Training and evaluation of the downstream SVM classifier on features extracted from the Transformer.

- **swin-unetr.ipynb**  
  Final, integrated inference pipeline using a Swin‑UNETR backbone for 3D segmentation and SVM for classification.

---
