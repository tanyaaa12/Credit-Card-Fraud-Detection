# Credit-Card-Fraud-Detection

Credit Card Fraud Detection Using Machine Learning

This project focuses on detecting fraudulent credit card transactions using machine learning and anomaly detection techniques. The dataset used is highly imbalanced, so different methods were applied to handle the class imbalance and improve fraud detection.


Dataset Used:
Source: Kaggle - Credit Card Fraud Dataset - (https://www.kaggle.com/mlg-ulb/creditcardfraud)   
Total Records: 284,807 transactions
Fraudulent Transactions: ~0.17%
Features: Anonymized (V1-V28), along with Time and Amount columns.


Steps and Approach:
1. Exploratory Data Analysis (EDA)
Checked class imbalance and distribution of features
Used histograms, boxplots, and correlation heatmaps to identify patterns
Standardized the Time and Amount columns using StandardScaler

2. Model Training (Supervised Learning)
Different Machine Learning models were trained and evaluated:
Logistic Regression
Random Forest
XGBoost

Random Forest performed the best in terms of accuracy & precision, while XGBoost achieved higher recall, meaning it detected more fraudulent transactions.


3. Anomaly Detection
Tried unsupervised learning methods to detect fraud without labeled data:
Isolation Forest did not perform well due to class imbalance.

Since fraudulent transactions are rare, we explored anomaly detection methods to detect fraud without relying on labeled data. 
One such method is Autoencoders, a type of neural network trained to reconstruct normal transactions and identify anomalies (fraudulent transactions) based on reconstruction errors.
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

4. Power BI Dashboard
Created a Power BI dashboard to visualize:
Fraud vs Non-Fraud Transactions
Transaction Amount Trends
Correlation Patterns
Fraud Distribution by Time

Power BI Dashboard Link :  
(https://svkmmumbai-my.sharepoint.com/:u:/g/personal/tanya_batra228_svkmmumbai_onmicrosoft_com/ESkQ5SCxcitBuQ4TN_tWdu4B_xfMRdv9HwIf_WL_2l71DA?e=kmwBqa) 
[View Power BI Dashboard](https://drive.google.com/drive/folders/14XU-dM2i66ZZtHyRj4QNLb1gqT2Q4R03?usp=drive_link)  

Key observations from the dashboard:
Fraud transactions tend to happen at specific time intervals.
The transaction amount is generally higher for fraudulent transactions.
Certain features (like V7 and Amount) have stronger correlations with fraud.




