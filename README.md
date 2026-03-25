# Parkinson-s-Diagnosis-Using-Voice-Signal-Analysis
A Julia-based machine learning project for Parkinson’s diagnosis using voice signals, including PCA, t-SNE, feature selection, and model evaluation.

Full academic report: [Report.pdf](./report.pdf)

---

## Overview

- Dataset: Voice recordings with ~754 features per sample  
- Task: Binary classification (PD vs Healthy)  

### Key Challenges
- High dimensionality → risk of overfitting  
- Class imbalance (PD > HC)  
- Repeated recordings per subject (risk of data leakage)  
- Strong feature correlations (redundancy)  

---

## Approach

### 1. Feature Exploration
- PCA → global structure  
- t-SNE → local clustering  
- SOM → topology analysis  

**Findings:**
- MFCC and TQWT features show better separability  
- Significant class overlap → non-linear classification problem  

---

### 2. Model Comparison

Models evaluated:
- Random Forest (RF)  
- Support Vector Machine (SVM)  
- K-Nearest Neighbours (KNN)  

**Key Results:**
- Random Forest achieved the most stable performance (~0.80–0.82 accuracy)  
- KNN and SVM were more sensitive to data variation  
- Ensemble models better capture non-linear relationships  

---

### 3. Feature Selection

Methods:
- Random Forest feature importance  
- Correlation filtering (Pearson)  

**Outcome:**
- Reduced features from ~754 → ~330  
- Maintained performance:
  - Accuracy ~0.82  
  - Balanced Accuracy ~0.69  
  - AUC ~0.85  

---

### 4. Robust Evaluation

To ensure reliable results:

- Grouped cross-validation (by subject)  
- Stratified sampling (handle class imbalance)  
- Nested cross-validation (5×5)  

**Results (after stricter validation):**
- Random Forest:
  - Accuracy ~0.76  
  - Balanced Accuracy ~0.71  
  - AUC ~0.82  
- KNN:
  - Lower but stable performance  

---

## Key Insights

- MFCC and TQWT are the most informative feature schemes  
- Random Forest provides the most stable and reliable performance  
- Feature selection effectively reduces dimensionality without performance loss  
- Proper validation (grouped + nested CV) is essential for real-world reliability  

---

## Tech Stack

- Julia  
- DataFrames  
- Machine Learning models (RF, SVM, KNN)  
- PCA, t-SNE, SOM  

---

## My Contribution

This was a group project. My primary contributions included:

- Data preprocessing and feature engineering  
- t-SNE and Random Forest analysis  
- Feature selection (Random Forest importance and correlation filtering)  
- Model training and evaluation  
- Refining and restructuring the notebook for clarity and reproducibility  

---

## 📚 Reference

Sakar et al. (2018) – Parkinson’s Disease Classification using Voice Signals

