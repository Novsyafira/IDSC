# IDSC

# Glaucoma Detection using Deep Learning (EfficientNet-B0)

[![Python 3.12](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-ee4c2c.svg)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## About This Project

**Glaucoma** is the leading cause of permanent blindness worldwide. Early diagnosis is crucial, yet it is often hindered by a shortage of ophthalmologists and the high cost of OCT equipment.

This project builds a **Computer-Aided Diagnosis (CAD)** system based on *Deep Learning* to detect Glaucoma (GON+) from fundus retina images. Our goal is to create a *pre-screening* tool that is accurate, fast, and interpretable, helping to prevent mass blindness by prioritizing high sensitivity.

> **Primary Objective:** Build a binary classification model that prioritizes **Sensitivity (Recall)** to minimize missed cases (False Negatives).


## Key Features

*   **High Sensitivity:** Achieved **98.0% Sensitivity**, ensuring almost all glaucoma patients are detected.
*   **Explainable AI (XAI):** Utilizes **Grad-CAM** to visualize the model's focus areas (Optic Disc), providing transparency for doctors.
*   **Robustness:** Trained with *Class Weighting* to handle data imbalance and maintain performance across varying image qualities.
*   **Efficient Architecture:** Uses **EfficientNet-B0** (Transfer Learning) for an optimal balance between accuracy and computational efficiency.


## Evaluation Results (Test Set)

The model was evaluated on the HYGD Test Set, achieving clinically significant results:

| Metric | Score | Clinical Note |
| :--- | :--- | :--- |
| **AUC-ROC** | **0.9962** | Near-perfect discrimination ability |
| **Accuracy** | **96.2%** | Overall accuracy |
| **Sensitivity** | **98.0%** | **Clinical Priority:** Only 2 out of 100 glaucoma patients missed |
| **Specificity** | **90.6%** | Successfully identifies healthy patients |
| **F1-Score** | **0.975** | Harmony between precision and recall |

### Performance Visualizations

#### 1. ROC Curve & Confusion Matrix
![ROC Curve](assets/roc_curve.png) *(Ensure you save your ROC plot images in an 'assets' folder)*

#### 2. Grad-CAM Visualization
The model consistently focuses on the **Optic Disc**, the critical area for glaucoma diagnosis.
![GradCAM](assets/gradcam_sample.png) *(Ensure you save your Grad-CAM images in an 'assets' folder)*


## Dataset Overview (HYGD)

*   **Total Images:** 747
*   **Unique Patients:** 288
*   **Classes:**
    *   **GON+ (Glaucoma):** 548 images (73.4%)
    *   **GON- (Normal):** 199 images (26.6%)
*   **Quality Score:** Varied (Min: 2.0, Max: 7.7), handling real-world image conditions.
*   **Imbalance Ratio:** 2.75:1 (Handled via Class Weights)
