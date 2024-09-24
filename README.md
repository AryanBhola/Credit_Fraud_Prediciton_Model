# Credit Card Fraud Detection Predictive Models

## Introduction
Credit card fraud is a significant challenge in the financial sector, and detecting fraudulent transactions in real-time is crucial for companies and cardholders. This project aims to develop and compare different predictive models for detecting fraudulent transactions using credit card data.

The dataset used in this project contains transactions made by European cardholders in September 2013. It includes a total of 284,807 transactions, out of which only 492 are fraudulent, accounting for 0.172% of the total. This high imbalance presents a challenge for standard machine learning techniques.

The features in the dataset are primarily numerical, transformed using Principal Component Analysis (PCA). The dataset includes two non-transformed features: **Time** (elapsed time since the first transaction) and **Amount** (transaction amount). The response variable, **Class**, indicates whether a transaction is fraudulent (Class = 1) or legitimate (Class = 0).

## Data Exploration Overview
In the data exploration phase, we examined key aspects of the dataset:

1. **Transaction Time Distribution**: Analyzed transaction distribution over time for both fraud and non-fraud classes.
2. **Hourly Aggregation**: Aggregated data by hour to study patterns in transaction count and amount.
3. **Transaction Amounts**: Used box plots to visualize distribution of amounts across classes.
4. **Amount Over Time**: Created scatter plots to highlight trends in fraudulent transactions.

## Step-by-Step Analysis Process

1. **Correlation Heatmap**: 
   - Objective: Visualize correlations between features.
   - Results: Minimal correlations among V1 to V28; notable correlations between Amount and features V7, V20.

2. **Linear Regression Analysis**: 
   - Objective: Confirm relationships between correlated features and Amount.
   - Results: Clear positive relationships for non-fraudulent transactions.

3. **Inverse Correlation Analysis**: 
   - Objective: Investigate negative correlations with Amount and Time.
   - Results: More pronounced inverse correlations in non-fraudulent transactions.

## Predictive Models Overview
We developed several machine learning classifiers:

1. **RandomForestClassifier**
   - **Introduction**: Ensemble method combining decision trees.
   - **Key Parameters**: `n_estimators`, `criterion`, `n_jobs`, `random_state`.
   - **Performance**: ROC-AUC score: **0.85**.

2. **AdaBoostClassifier**
   - **Introduction**: Boosting method combining weak classifiers.
   - **Key Parameters**: `n_estimators`, `algorithm`, `learning_rate`.
   - **Performance**: ROC-AUC score: **0.83**.

3. **CatBoostClassifier**
   - **Introduction**: Gradient boosting algorithm optimized for categorical data.
   - **Key Parameters**: `iterations`, `learning_rate`, `depth`.
   - **Performance**: ROC-AUC score: **0.86**.

## Error Types
- **Type I Error (False Positive)**: Transaction mistakenly identified as fraudulent.
- **Type II Error (False Negative)**: Fraudulent transaction incorrectly classified as legitimate.

Minimizing both error types is essential for effective fraud detection.

## Performance Evaluation
The primary evaluation metric is the ROC-AUC score, indicating the model's ability to differentiate between fraudulent and legitimate transactions.

## References
1. [Credit Card Fraud Detection Database](https://www.kaggle.com/datasets/dalpozz/creditcard-fraud)
2. [Principal Component Analysis - Wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)
3. [RandomForestClassifier - scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
4. [ROC-AUC characteristic - Wikipedia](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)
5. [AdaBoostClassifier - scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostClassifier.html)
6. [CatBoostClassifier - Yandex](https://catboost.ai/en/docs/concepts/python-api/)
