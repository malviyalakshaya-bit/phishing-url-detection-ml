# Phishing URL Detection Using Machine Learning

## Overview

This project presents a comparative study of machine learning algorithms for detecting phishing and legitimate websites. The study uses the PhiUSIIL Phishing URL Dataset and evaluates three supervised machine learning models: Logistic Regression, Linear Support Vector Machine (Linear SVM), and Random Forest.

The models are compared using standard classification metrics, and Random Forest feature importance is used to identify the most influential features. A feature ablation study is also performed by removing the `URLSimilarityIndex` feature to examine its effect on model performance.

## Dataset

The project uses the PhiUSIIL Phishing URL Dataset from the UCI Machine Learning Repository.

- Total instances: 235,795
- Original attributes: 54
- Numerical features used: 50
- Textual attributes removed: `URL`, `Domain`, `TLD`, and `Title`
- Train-test split: 80:20
- Split method: Stratified train-test split

Dataset:
https://archive.ics.uci.edu/dataset/967/phiusil-phishing-url-dataset

## Machine Learning Models

The following models were implemented:

1. Logistic Regression
2. Linear Support Vector Machine (Linear SVM)
3. Random Forest

StandardScaler was applied to Logistic Regression and Linear SVM. Random Forest was trained using the original numerical features.

## Evaluation Metrics

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix
- ROC Curve

## Results

| Model | Accuracy (%) | Precision (%) | Recall (%) | F1-Score (%) | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 99.9873 | 99.9778 | 100.0000 | 99.9889 | 0.99999998 |
| Linear SVM | 99.9915 | 99.9852 | 100.0000 | 99.9926 | 0.99999999 |
| Random Forest | 100.0000 | 100.0000 | 100.0000 | 100.0000 | 1.00000000 |

Random Forest achieved the best overall performance on the test set.

## Feature Importance

Random Forest feature importance analysis identified `URLSimilarityIndex` as the most influential feature, followed by features such as:

- `NoOfExternalRef`
- `LineOfCode`
- `NoOfSelfRef`
- `NoOfImage`
- `NoOfJS`

## Feature Ablation Study

To examine the contribution of `URLSimilarityIndex`, the feature was removed and all three models were retrained.

| Model | All Features (%) | Without URLSimilarityIndex (%) |
|---|---:|---:|
| Logistic Regression | 99.9873 | 99.9152 |
| Linear SVM | 99.9915 | 99.9830 |
| Random Forest | 100.0000 | 99.9894 |

The results show that removing `URLSimilarityIndex` slightly reduced the performance of Logistic Regression and Random Forest, while Linear SVM showed a marginal improvement.

## Project Workflow

Dataset
↓
Data Preprocessing
↓
Removal of Textual Attributes
↓
50 Numerical Features
↓
80:20 Stratified Split
↓
Feature Scaling
↓
Model Training
↓
Model Evaluation
↓
Feature Importance Analysis
↓
Feature Ablation Study

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## How to Run

1. Download or clone this repository.
2. Open `phishing_url_detection.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required Python libraries.
4. Obtain the PhiUSIIL dataset from the UCI Machine Learning Repository.
5. Run the notebook cells from beginning to end.

## Research Paper

This repository supports the research paper:

**A Comparative Study of Machine Learning Algorithms for Phishing URL Detection**

The paper compares Logistic Regression, Linear SVM, and Random Forest and includes feature importance and feature ablation analysis.

## Author

Lakshaya Malviya
