# Data Mining Using KNIME

## Overview
This repository contains two KNIME projects: **Classification Techniques using KNIME** and **Clustering Algorithms in KNIME**.

For classification, the **Forest Cover Type Dataset** was sampled and preprocessed before model development. Separate KNIME workflow files (`.knwf`) were used to train and test **Naive Bayes**, **Decision Tree**, **K-Nearest Neighbors (KNN)**, **Support Vector Machine (SVM)**, and **Neural Network** models. A report compares these models using **accuracy, precision, recall, F1-score, and confusion matrices**, then explains the selected best-performing algorithm and why it is suitable.

For clustering, the **Credit Card Dataset** was sampled and preprocessed before model development. Separate KNIME workflow files (`.knwf`) were used to train and test **K-Means Clustering**, **Hierarchical Clustering 2**, and **DBSCAN**, with visualizations where needed. Model comparison was performed using **Silhouette Score**, **visual quality of clusters**, and **computational efficiency (processing time)**. 

## Classification on Forest Cover Type Dataset

### Overview

This project applies supervised machine learning techniques in KNIME to predict forest cover types using the Forest Cover Type dataset. Five classification algorithms were implemented and evaluated: Naïve Bayes, Decision Tree, K-Nearest Neighbors (KNN), Support Vector Machine (SVM) with an RBF kernel, and Neural Network. The project covers data preprocessing, feature selection, model training, and performance evaluation to identify the most suitable classification algorithm for the dataset.

### Objectives

- Implement and compare five classification algorithms using KNIME.
- Prepare the dataset through missing-value handling, normalization, and feature selection.
- Evaluate model performance using accuracy, precision, recall, F1-score, and confusion matrices.
- Select the most suitable algorithm based on the evaluation results.

### Workflow

The classification process consists of the following stages:

1. **Data Import:** Load the Forest Cover Type dataset using the CSV Reader node.
2. **Data Preprocessing:** Convert the target variable `Cover_Type` to a categorical value, handle outliers and missing values, and normalize continuous features.
3. **Feature Selection:** Apply Pearson correlation analysis and a correlation filter with a threshold of 0.8 to reduce redundant continuous features.
4. **Data Sampling:** Use stratified sampling to select 100,000 records with a fixed random seed of 12345.
5. **Model Training and Testing:** Split the data into 70% training and 30% testing sets, stratified by `Cover_Type`.
6. **Model Evaluation:** Evaluate predictions using KNIME's Scorer node and compare the resulting metrics.

### Algorithms Evaluated

- **Naïve Bayes**
- **Decision Tree** — Gini impurity
- **K-Nearest Neighbors (KNN)** — k = 5, Euclidean distance
- **Support Vector Machine (SVM)** — RBF kernel
- **Neural Network** — RProp multilayer perceptron with one hidden layer of 10 neurons

Each algorithm was implemented in a separate KNIME workflow.

### Results and Model Comparison

| Algorithm | Accuracy |
|---|---:|
| Naïve Bayes | 63.3% |
| Decision Tree | 80.6% |
| K-Nearest Neighbors (KNN) | 80.8% |
| Support Vector Machine (SVM, RBF) | **81.9%** |
| Neural Network | 68.3% |

SVM with an RBF kernel achieved the highest accuracy at 81.9%, followed closely by KNN and Decision Tree. Naïve Bayes recorded the lowest accuracy, while the Neural Network achieved moderate performance.

Precision, recall, F1-score, and confusion matrices were also examined to assess class-level performance. ROC curves and AUC results were not available for this seven-class classification task in the implemented KNIME evaluation.

### Selected Model

**Support Vector Machine (RBF kernel)** was selected as the best-performing algorithm based on its highest observed accuracy.

The selection also considered its ability to model nonlinear relationships and the preprocessing steps used in the workflow, including feature scaling, feature selection, and stratified sampling. The reported results support its selection among the five evaluated models; they do not establish that it outperforms every possible alternative.

### Repository Contents

- **Workflow Documentation:** Describes the KNIME nodes, configurations, and processing steps.
- **Results and Analysis Report:** Presents model comparisons, evaluation findings, and the model-selection rationale.
- **KNIME Workflows:** Separate workflows for preprocessing, model implementation, and evaluation.
- **Images:** Selected screenshots of the workflow, model comparison, and evaluation results.

### Tools and Technologies

- KNIME Analytics Platform
- Forest Cover Type dataset
- Supervised machine learning
- Data preprocessing and feature selection
- Classification model evaluation

### Conclusion

Five classification algorithms were implemented and compared using KNIME. SVM with an RBF kernel achieved the highest accuracy of 81.9% and was selected as the most suitable model among those evaluated. The project demonstrates a complete classification workflow, from data preparation and feature selection to model evaluation and comparison.


## Clustering on Credit Card Dataset
