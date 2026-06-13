# Breast Cancer Diagnosis Using Logistic Regression

## Overview

This project applies Logistic Regression to classify breast tumors as benign or malignant using the Breast Cancer Wisconsin (Diagnostic) dataset from the UCI Machine Learning Repository.

The study combines statistical feature selection using the Mann–Whitney U test with machine learning classification to identify the most important predictors of malignancy.

## Dataset

**Dataset:** Breast Cancer Wisconsin (Diagnostic)

* Instances: 569
* Features: 30
* Target Variable: Diagnosis (Malignant = M, Benign = B)
* Source: UCI Machine Learning Repository
* DOI: 10.24432/C5DW2B

The dataset contains measurements extracted from digitized images of fine needle aspirates (FNA) of breast masses.

## Methodology

### Data Preparation

* Retrieved data using the `ucimlrepo` package.
* Combined features and diagnosis labels into a single dataframe.
* Encoded diagnosis:

  * Malignant (M) = 1
  * Benign (B) = 0

### Feature Selection

A Mann–Whitney U Test was performed on all 30 predictors to determine whether feature distributions differed significantly between benign and malignant tumors.

The ten most significant features were selected for modeling.

### Selected Features

1. perimeter3
2. radius3
3. area3
4. concave_points3
5. concave_points1
6. perimeter1
7. area1
8. concavity1
9. radius1
10. area2

### Model Development

* Train-test split: 80%-20%
* Stratified sampling
* Feature standardization using StandardScaler
* Logistic Regression classifier

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix

## Results

| Metric    | Value  |
| --------- | ------ |
| Accuracy  | 96.49% |
| Precision | 97.50% |
| Recall    | 92.86% |
| F1 Score  | 0.9512 |
| AUC-ROC   | 99.77% |

### Confusion Matrix

|                  | Predicted Benign | Predicted Malignant |
| ---------------- | ---------------- | ------------------- |
| Actual Benign    | 71               | 1                   |
| Actual Malignant | 3                | 39                  |

The model demonstrates excellent discriminative ability with a near-perfect ROC-AUC score.

## Visualizations

The notebook includes:

* Mann–Whitney U Test significance plot
* Feature distribution boxplots
* Logistic Regression coefficient analysis
* Confusion Matrix heatmap
* ROC Curve

## Key Findings

* Features related to tumor size and boundary irregularity were the strongest predictors of malignancy.
* The most influential variables included perimeter3, radius3, area3, and concave_points3.
* Logistic Regression achieved high predictive performance while remaining interpretable.

## Technologies Used

* Python
* Pandas
* NumPy
* SciPy
* Scikit-learn
* Matplotlib
* Seaborn
* UCI ML Repository API

## References

Street, W. N., Wolberg, W. H., & Mangasarian, O. L. (1993). Nuclear Feature Extraction for Breast Tumor Diagnosis.

Dataset DOI: 10.24432/C5DW2B

