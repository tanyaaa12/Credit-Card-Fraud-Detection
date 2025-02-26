# Credit-Card-Fraud-Detection

Credit Card Fraud Detection Using Machine Learning

This project focuses on detecting fraudulent credit card transactions using machine learning and anomaly detection techniques. The dataset used is highly imbalanced, so different methods were applied to handle the class imbalance and improve fraud detection.

Dataset
Source: Kaggle - Credit Card Fraud Dataset - (https://www.kaggle.com/mlg-ulb/creditcardfraud)   
Contains 284,807 transactions with only 0.17% labeled as fraud
Features are anonymized (V1-V28) with additional columns: Time and Amount

Steps and Approach
1. Exploratory Data Analysis (EDA)
Checked class imbalance and distribution of features
Used histograms, boxplots, and correlation heatmaps to identify patterns
Standardized the Time and Amount columns using StandardScaler

2. Model Training (Supervised Learning)
Trained different machine learning models and compared performance:

Model	Accuracy	Precision	Recall	AUC-ROC
Logistic Regression	97.42%	5.81%	91.83%	94.63%
Random Forest	99.94%	84.54%	83.67%	91.82%
XGBoost	99.92%	73.11%	88.78%	94.36%
Random Forest performed best in terms of accuracy and precision.
XGBoost had high recall, meaning it detected more fraudulent transactions.

3. Anomaly Detection
Tried unsupervised learning methods to detect fraud without labeled data:
Isolation Forest did not perform well due to class imbalance.

Since fraudulent transactions are rare, we explored anomaly detection methods to detect fraud without relying on labeled data. One such method is Autoencoders, a type of neural network trained to reconstruct normal transactions and identify anomalies (fraudulent transactions) based on reconstruction errors.
Traditional ML models require labeled data, but fraud cases are limited, making supervised learning less effective.
Autoencoders learn the normal transaction patterns and flag transactions that deviate significantly.
They are useful for unsupervised fraud detection, where new fraud patterns may emerge over time.
Approach:
Trained the autoencoder on non-fraud transactions only.
Reconstructed transactions and calculated reconstruction error.
Set a threshold: Transactions with high errors were classified as fraud.
Results:
The autoencoder was able to detect some fraudulent transactions but required fine-tuning for better precision.
Compared to traditional ML models, autoencoders offer a flexible approach but need careful threshold selection.

5. Power BI Dashboard
A Power BI dashboard was created to analyze fraud trends, transaction patterns, and correlations.

Power BI Dashboard Link

Key observations from the dashboard:

Fraud transactions tend to happen at specific time intervals.
The transaction amount is generally higher for fraudulent transactions.
Certain features (like V7 and Amount) have stronger correlations with fraud.
How to Run
To train the models:

Open fraud_detection.ipynb in Google Colab
Install dependencies:
bash
pip install -r requirements.txt
Run all cells to train models and evaluate performance


To view the Power BI dashboard:
Open Power BI Desktop

Explore fraud trends and model results
