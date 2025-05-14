# Heart Disease Prediction with EDA using UCI Dataset

## Project Summary

This project explores medical data related to heart disease, applying Exploratory Data Analysis (EDA) and classification modeling using a Decision Tree. The dataset comes from the UCI Machine Learning Repository and contains 303 patient records. The work is conducted as part of a Data Scientist certification exam practice and written in Bahasa Indonesia.

## 📁 Dataset
[![UCI Dataset](https://img.shields.io/badge/UCI%20Dataset-Heart%20Disease-orange?logo=data)](https://archive.ics.uci.edu/dataset/45/heart+disease)

### ⭐ Situation

Heart disease remains one of the deadliest conditions globally. Early detection through data can assist healthcare professionals and public health authorities in diagnosing and intervening. The Indonesian government encourages digital medical records for patients, providing opportunities to train models that predict health outcomes based on real-world attributes.

### ⭐ Task

The objective of this project is to:
- Identify key variables that influence heart disease conditions.
- Perform EDA to extract statistical patterns and correlations.
- Build and evaluate a classification model to predict heart disease levels.
- Understand model performance issues, particularly under class imbalance conditions.

### ⭐ Action

- The dataset includes 13 numeric features (e.g., age, cholesterol, blood pressure) and a target variable `num` (0–4 indicating disease severity).
- Conducted statistical description, histogram analysis, correlation heatmap, and boxplot visualizations for each feature.
- Identified missing values in `ca` and `thal`, which were minimal (~1%).
- Built a baseline **Decision Tree classifier**, then optimized using hyperparameter tuning (`max_depth`, `min_samples_split`, `min_samples_leaf`).
- Evaluated using metrics: accuracy, precision, recall, confusion matrix, and cross-validation.

### ⭐ Result

- Class distribution was heavily imbalanced: 54% of patients were labeled as `0` (no heart disease), while class `4` only represented ~4%.
- EDA revealed:
  - Features like `thal`, `ca`, and `oldpeak` were positively correlated with heart disease.
  - Features like `thalach` (max heart rate) showed negative correlation.
- Baseline Decision Tree results:
  - Accuracy: 51.6%
  - Precision: 51.6%
  - Recall: 51.6%
- After tuning:
  - Accuracy dropped to 45.2% due to better generalization but lower sensitivity to minority classes.
  - Cross-validation score improved to 55.5%, but test performance dropped—suggesting overfitting in the training phase.
- The model struggled with minority classes (1–4), especially for class 4, where no true positives were predicted.

## 📊 Key Insights

- The majority of patients are male and within the 50–60 year age range.
- Patients with asymptomatic chest pain (cp=4), high oldpeak values, and more major vessels affected (ca > 1) are more likely to suffer from heart disease.
- The target `num` has five classes (0–4), making this a **multiclass classification** problem, not binary.
- Class imbalance poses a major challenge, with class 0 dominating the dataset.
- Decision Tree modeling performed moderately well on dominant class (0), but poorly on minority classes.
