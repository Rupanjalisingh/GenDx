# GenDx: GenAI-Based Augmentation for Improved Medical Image Diagnosis

## Overview

GenDx is a deep learning framework for multi-class cancer image classification that investigates the impact of Generative AI-inspired data augmentation on medical image diagnosis. The project focuses on improving classification performance, addressing class imbalance, enhancing model explainability, and providing comprehensive evaluation and visualization tools.

The system classifies 26 cancer-related classes across multiple organs and disease stages using convolutional neural networks and synthetic image augmentation strategies.

---

# Project Objectives

* Build a multi-class cancer image classification system.
* Handle class imbalance in medical imaging datasets.
* Generate synthetic samples using GenAI-inspired augmentation.
* Improve diagnostic accuracy through data enrichment.
* Provide explainable AI outputs using Grad-CAM.
* Analyze model performance through extensive statistical evaluation.

---

# Dataset

The project uses a multi-cancer image dataset containing:

### Cancer Categories

#### ALL (Acute Lymphoblastic Leukemia)

* all_benign
* all_early
* all_pre
* all_pro

#### Brain Cancer

* brain_glioma
* brain_menin
* brain_tumor

#### Breast Cancer

* breast_benign
* breast_malignant

#### Cervical Cancer

* cervix_dyk
* cervix_koc
* cervix_mep
* cervix_pab
* cervix_sfi

#### Colon Cancer

* colon_aca
* colon_bnt

#### Kidney Cancer

* kidney_normal
* kidney_tumor

#### Lung Cancer

* lung_aca
* lung_bnt
* lung_scc

#### Lymphoma

* lymph_cll
* lymph_fl
* lymph_mcl

#### Oral Cancer

* oral_normal
* oral_scc

Total Classes: 26

---

# Model Architecture

* Framework: PyTorch
* Backbone: EfficientNet-based CNN
* Loss Function: CrossEntropyLoss
* Optimizer: Adam
* Learning Rate: 1e-4
* Epochs: 5
* Batch Size: 16

---

# Experiments

## Experiment 1: Baseline Model

Training on original dataset.

Validation Accuracy:

94.42%

---

## Experiment 2: Imbalanced Dataset

Artificially reduced samples from selected classes.

Validation Accuracy:

94.27%

---

## Experiment 3: Traditional Augmentation

Applied:

* Horizontal Flip
* Rotation
* Random Crop
* Color Jitter

Validation Accuracy:

94.27%

---

## Experiment 4: GenAI-Based Augmentation

Generated synthetic images for minority classes:

* brain_glioma
* kidney_tumor
* lymph_mcl
* oral_scc

Generated Samples:

1200

Final Dataset Size:

6000

Validation Accuracy:

95.58%

Test Accuracy:

94.84%

---

# Explainability

Grad-CAM was used to visualize model attention regions.

Outputs include:

* Original Image
* Heatmap Overlay
* Predicted Class
* Confidence Score

This improves transparency and interpretability of model predictions.

---

# Evaluation Metrics

The project evaluates:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix
* Cohen's Kappa
* Matthews Correlation Coefficient (MCC)
* Confidence Analysis
* Per-Class Accuracy

---

# Visualizations

Generated Outputs:

* Confusion Matrix Heatmap
* Per-Class Accuracy Plot
* ROC Curves
* Confidence Distribution
* t-SNE Feature Visualization
* Misclassified Image Gallery
* Grad-CAM Gallery
* Cancer Atlas Dashboard
* Model Comparison Plot

---

# Project Structure

```text
GenDx/
│
├── data/
├── models/
├── outputs/
├── src/
│   ├── train.py
│   ├── train_imbalanced.py
│   ├── train_augmented.py
│   ├── train_genai.py
│   ├── evaluate_genai.py
│   ├── gradcam.py
│   └── dataset.py
│
├── Other_analysis*.py
├── README.md
└── requirements.txt
```

---

# Results Summary

| Model      | Validation Accuracy |
| ---------- | ------------------- |
| Baseline   | 94.42%              |
| Imbalanced | 94.27%              |
| Augmented  | 94.27%              |
| GenAI      | 95.58%              |

Best Model:

GenAI-Augmented CNN

---

# Limitations

Although the proposed framework achieved improved performance, several limitations remain:

1. Synthetic images were generated using augmentation techniques rather than large diffusion-based medical foundation models.

2. Dataset diversity may not fully represent real-world hospital populations.

3. Only image data was used. Clinical metadata was not incorporated.

4. Evaluation was performed on a single dataset split without external validation.

5. Model performance may decrease when deployed on images acquired from different scanners or institutions.

6. Grad-CAM provides approximate explanations and should not be considered definitive clinical evidence.

7. The system is intended for research purposes only and is not approved for clinical diagnosis.

8. Additional testing on larger multi-center datasets is required before real-world deployment.

---

# Future Work

* Diffusion-based medical image generation.
* Vision Transformers (ViT).
* Self-supervised pretraining.
* Federated learning.
* Multi-modal learning using clinical metadata.
* Deployment using Streamlit or FastAPI.
* Real-time diagnostic dashboard.
* Integration with pathology and radiology workflows.

---

# Author

Rupanjali Singh



