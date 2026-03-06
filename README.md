# Credit_Card_Fraud_Detection
Machine Learning project to detect fraudulent credit card transactions using a highly imbalanced real-world dataset.

The goal of this project is to build a classification model that can accurately identify fraudulent transactions while minimizing false negatives, since missing a fraud transaction can lead to financial loss.

Problem Statement

Credit card fraud causes significant financial losses for banks and customers worldwide.
However, fraud transactions are extremely rare compared to legitimate ones.

This creates a highly imbalanced classification problem, where traditional accuracy metrics can be misleading.

The objective of this project is to:

Identify patterns in transaction data

Build models to classify transactions as Fraud or Legitimate

Evaluate models using metrics suitable for imbalanced datasets

Dataset

The dataset used in this project is the ULB Credit Card Fraud Detection dataset from Kaggle.

Dataset characteristics:

Total transactions: 284,807

Fraudulent transactions: 492

Fraud percentage: 0.17%

Features include:

V1 – V28 : PCA-transformed numerical features

Time : Seconds elapsed between transactions

Amount : Transaction amount

Class : Target variable

0 → Legitimate transaction

1 → Fraudulent transaction

The PCA transformation was applied to protect sensitive financial information.

Key Challenges

The dataset presents several challenges:

Extreme class imbalance

Accuracy is not a reliable metric

False negatives are very costly

Need for careful model evaluation

Because of this, the focus is on Recall and ROC-AUC instead of accuracy.

Exploratory Data Analysis

Exploratory analysis was performed to understand transaction patterns.

Key observations:

Fraud transactions make up only 0.17% of the dataset

Fraud transactions often involve smaller amounts

PCA features show some separability between fraud and legitimate transactions

Time and amount alone are weak predictors but useful when combined with other features

Data Preprocessing

Several preprocessing steps were performed:

Stratified train-test split (80/20) to preserve class distribution

Scaling applied to Time and Amount features

PCA features were already standardized

Scaling applied after train-test split to avoid data leakage

Models Used

Two machine learning models were implemented:

Logistic Regression

Used as a baseline model.

Advantages:

Simple

Interpretable

Performs well on linearly separable data

Random Forest

Used as a non-linear model for comparison.

Advantages:

Handles complex relationships

Robust to overfitting

Provides feature importance

Evaluation Metrics

Since the dataset is highly imbalanced, several metrics were used:

Precision → Accuracy of fraud predictions

Recall → Ability to detect actual fraud cases

F1-score → Balance between precision and recall

ROC-AUC → Overall classification performance

Recall is the most important metric because missing fraud transactions is costly.

Results
Logistic Regression

Recall ≈ 0.92

ROC-AUC ≈ 0.97

Random Forest

Higher precision

Recall ≈ 0.74

ROC-AUC ≈ 0.95

Logistic Regression performed better for this dataset, likely because PCA-transformed features favor linear decision boundaries.

Technologies Used

Python

Pandas

NumPy

Scikit-learn

Matplotlib

Jupyter Notebook

Future Improvements

Possible improvements for this project:

Implement SMOTE to handle class imbalance

Experiment with Gradient Boosting / XGBoost

Apply threshold tuning to improve recall

Use cost-sensitive learning

Deploy model using Flask or FastAPI

Conclusion

This project demonstrates how machine learning can be applied to detect fraudulent credit card transactions.

Despite the extreme class imbalance, appropriate preprocessing and evaluation techniques allow models to effectively identify fraud patterns.

Logistic Regression performed better than Random Forest due to the nature of the PCA-transformed features.
