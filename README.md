# Maternal Morbidity Risk Profiling

### Machine Learning Pipeline for Latent Profile Discovery

End-to-end machine learning pipeline organized across modular notebooks.

---

## Overview

This repository contains the full analytical pipeline for identifying latent maternal risk profiles and modeling maternal morbidity using U.S. natality data.

The project focuses on applying unsupervised learning and predictive modeling techniques to explore heterogeneous risk structures within maternal populations using pre-delivery characteristics.

The workflow is structured as a sequential pipeline across modular notebooks to ensure clarity and reproducibility.

---

## What This Repository Contains

* End-to-end data preprocessing workflow
* Dimensionality reduction using PCA
* Clustering implementation (K-Means)
* Statistical modeling (logistic regression)
* Predictive modeling (ensemble + linear models)
* Class imbalance handling and threshold optimization

---

## Methodological Pipeline

### 1. Data Preprocessing

* Missing value handling
* Encoding categorical variables
* Feature selection across multiple maternal health domains

---

### 2. Dimensionality Reduction

* Principal Component Analysis (PCA)
* Retains ~92% of variance

---

### 3. Clustering

* K-Means clustering applied to PCA-transformed data
* Optimal cluster selection using:

  * Elbow method
  * Silhouette score

---

### 4. Statistical Modeling

* Logistic regression (statsmodels)
* Estimation of odds ratios and confidence intervals
* Chi-square tests for association

---

### 5. Predictive Modeling

Models implemented:

* Logistic Regression
* Random Forest
* XGBoost
* LightGBM

#### Handling Class Imbalance

* Class weighting
* SMOTE (training data only)
* `scale_pos_weight` for boosting models

#### Evaluation Metrics

* Precision, Recall, F1-score
* ROC-AUC, PR-AUC

#### Threshold Optimization

* Precision-recall curve analysis
* F1-score maximization

---

## Repository Structure

```
maternal-morbidity-risk-profiles/
│
├── notebooks/        # Jupyter notebooks for analysis pipeline
├── src/              # Reusable Python scripts
├── data/             # Dataset instructions (no raw data included)
├── README.md
└── requirements.txt
```

---

## Notebook Workflow

The analysis is organized into four sequential notebooks:

1. **01_data_cleaning.ipynb**
   Data preprocessing, cleaning, and feature preparation

2. **02_pca_clustering.ipynb**
   Dimensionality reduction (PCA) and K-Means clustering

3. **03_profile_outcome_association.ipynb**
   Statistical analysis including chi-square tests and logistic regression

4. **04_predictive_modeling.ipynb**
   Machine learning models and performance evaluation

Notebooks are designed to be run in order, as outputs from earlier steps are used in later stages.

---

## Data Access

The dataset used in this project is publicly available from the CDC Natality Data repository.

Due to size and usage constraints, raw data is not included.

https://www.cdc.gov/nchs/data_access/vitalstatsonline.htm

---

## Notes

This repository is intended to demonstrate the technical implementation of a machine learning pipeline for healthcare data analysis.

Outputs, results, and full report documentation are maintained separately and can be provided upon request.

---

## Tools & Technologies

* Python  
* pandas, NumPy  
* scikit-learn (PCA, K-Means, Logistic Regression, Random Forest)  
* statsmodels 
* SciPy 
* XGBoost, LightGBM  
* imbalanced-learn (SMOTE)  
* Matplotlib, Seaborn, Plotly  

---

## Author

Ariana Baker
M.S. Biomedical Data Science
Meharry Medical College

---

## Summary

This repository highlights the implementation of a scalable, end-to-end machine learning workflow for analyzing high-dimensional healthcare data, with emphasis on clustering, statistical modeling, and predictive performance under class imbalance.
