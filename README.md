# Multimodal Machine Learning for Thyroid Carcinoma Detection
## Pathomics and Ultrasound Radiomics

This repository contains research code, experiments, and supporting materials for multimodal deep learning–based detection of Papillary Thyroid Carcinoma (PTC) using paired ultrasound images and cytological images.

The study investigates whether combining ultrasound radiomics with cytology pathomics improves thyroid cancer classification performance compared to single-modality approaches.

---

## Research Motivation

Research Paper: https://github.com/NuaeserTasin500/Multimodal-ML-for-PTC-Detection-/raw/main/Multimodal%20Machine%20Learning%20for%20Thyroid%20Carcinoma%20Detection%20(Pathomics%20and%20Ultrasound%20Radiomics).pdf

Conventional thyroid cancer diagnosis relies heavily on:

- Ultrasound imaging
- Fine Needle Aspiration (FNA)
- Cytological examination

Both methods have limitations when used independently.

This work explores multimodal learning to combine complementary diagnostic information from:

- **Ultrasound images (Radiomics)**
- **Cytological images (Pathomics)**

for improved Papillary Thyroid Carcinoma classification.

---

## Objectives

- Build multimodal ML models for thyroid carcinoma detection
- Compare single-modality and multimodal approaches
- Perform feature fusion across imaging modalities
- Evaluate interpretability using Grad-CAM
- Analyze classification performance using multiple metrics

---

## Dataset

Dataset Link: https://data.mendeley.com/datasets/dp7zp2pb2v/1

The study uses paired datasets containing:

- Ultrasound images
- H&E stained cytological images
- Binary labels:
  - 0 → Benign
  - 1 → Papillary Thyroid Carcinoma (PTC)

Patient-level stratification was maintained to reduce data leakage.

Dataset split:

- Train: 70%
- Validation: 15%
- Test: 15%

---

## Research Code

Code: https://drive.google.com/drive/u/0/folders/1hgvLohNn6jM50KgpO-jqeBLNieAkMml4

---

## Preprocessing

Applied preprocessing includes:

- Resize → 224 × 224
- Random horizontal flipping
- Random rotation
- Color jitter
- Tensor normalization
- ImageNet statistics normalization

---

## Models Evaluated

### Cytology-only Models

- EfficientNet-B3
- EfficientNet-B4
- EfficientNetV2
- Swin Transformer Tiny

### Ultrasound Baseline

- EfficientNet-B4

### Multimodal Fusion Models

- EfficientNet-B3 Fusion
- Hybrid EfficientNetV2
- ResNet50 Fusion
- Cross-Attention Fusion
- Ensemble Fusion Architectures

---

## Proposed Multimodal Architecture

The fusion framework combines:

Ultrasound Encoder (EfficientNet-B4)

+

Cytology Encoder (EfficientNet-B4)

↓

Feature Concatenation (3584-D)

↓

MLP Classifier Head

↓

Binary Classification

(Benign / PTC)

The architecture uses late fusion and feature-level integration.

---

## Evaluation Metrics

Performance evaluated using:

- Accuracy
- Weighted F1-score
- Macro F1-score
- ROC-AUC
- Precision-Recall AUC
- Confusion Matrix

---

## Interpretability

Grad-CAM visualization was applied to analyze:

- Ultrasound attention regions
- Cytological nuclear features
- Model decision transparency

This helps verify clinically meaningful feature learning.

---

## Results

Key findings from experiments:

- Multimodal fusion consistently outperformed single-modality baselines
- Best fusion model achieved:

Accuracy ≈ 93.95%

Weighted F1 ≈ 0.9395

- Fusion models showed improved robustness through complementary modality information

---
