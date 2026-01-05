# Machine learning–based prediction of severe neurocognitive impairment phenotype in ACS

## Project Overview
This repository contains the analytical pipeline for the paper: *"Machine learning–based prediction of severe neurocognitive impairment phenotype in acute coronary syndrome"*. 

The primary goal is to use **Supervised Machine Learning** to predict and validate neurocognitive phenotypes (clusters) previously identified through unsupervised learning (K-Means).

## Study Design: Supervised Validation of Clusters
The identification of clusters is an unsupervised process. To ensure these groups represent distinct clinical entities rather than statistical noise, we implemented a **cross-model validation framework**:
1. **Separability:** If supervised models can accurately predict cluster membership, the clusters are statistically distinct.
2. **Consistency:** Identifying the same key predictors across different architectures (Linear, Tree-based, and Kernel-based) validates the clinical phenotype.

## Key Results
- **Top Performance:** Non-linear models reached high discriminative power, with **XGBoost (AUC = 0.959)** and **SVM (AUC = 0.837)**.
- **Primary Predictor:** **Depressive Symptoms (HADS-D)** emerged as the most robust predictor of the severe phenotype across all 7 models.
- **Clinical Risk:** Logistic Regression identified HADS-D (OR = 1.10) and female Gender (OR = 0.43) as significant independent predictors.

## Repository Structure
- `/data`: Contains processed data objects (`.rds`).
- `/scripts`: Full R pipeline from preprocessing to benchmark.
- `/outputs_tables`: Tables with AUC benchmarks and Odds Ratios.
- `/outputs_plots`: ROC curves and Feature Importance visualizations.

## Requirements
R packages: `tidyverse`, `caret`, `pROC`, `xgboost`, `randomForest`, `e1071`, `nnet`.
