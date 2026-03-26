Telecom Customer Churn Prediction
Problem Statement & Objective
Problem Statement

Customer churn is a critical issue for telecom companies as it directly affects revenue. The goal of this project is to predict whether a customer will leave (churn) based on their demographic, usage, and billing information.

Objectives
Build machine learning models to predict customer churn
Perform data preprocessing and feature engineering
Train and compare multiple models including Logistic Regression and Random Forest
Optimize model performance using hyperparameter tuning
Evaluate models using Accuracy, Precision, Recall, F1-score, and ROC-AUC
Provide actionable insights for business strategy and retention
Dataset Used
Dataset: Telco Customer Churn (IBM Sample Dataset)
Source: Telco Customer Churn CSV
Rows: ~7,000
Features: 20+ features including demographic info, services subscribed, and billing info
Target: Churn (Yes/No)
Preprocessing & Feature Engineering
Numerical Features:
Imputed missing values using median
Standardized using StandardScaler
Categorical Features:
Imputed missing values using most frequent
Encoded using OneHotEncoding
Class Imbalance:
Handled via class weights in model training
Train/Test Split: Stratified split to preserve class distribution
Models Applied
Logistic Regression (Baseline & Tuned)
Random Forest Classifier (Baseline & Tuned)
Hyperparameter Tuning: GridSearchCV with StratifiedKFold
Evaluation Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC
Feature Importance: Extracted from Random Forest
Key Results and Findings
Model Performance
Model	Accuracy	Precision	Recall	F1	ROC-AUC
Logistic Regression (Baseline)	0.79	0.63	0.51	0.57	0.79
Logistic Regression (Tuned)	0.81	0.65	0.54	0.59	0.81
Random Forest (Baseline)	0.81	0.66	0.56	0.61	0.83
Random Forest (Tuned)	0.83	0.69	0.58	0.63	0.85
Feature Importance (Top Features from Random Forest)
Tenure
Contract type
Monthly charges
Payment method
Total charges
Business Insights
Customers with short tenure are more likely to churn
Month-to-month contract holders have higher churn risk
Higher monthly charges are correlated with churn
Limitations
Target variable is imbalanced; class weighting was used to mitigate this
Model performance could be improved using ensemble methods like XGBoost or LightGBM
Future Improvements
Apply oversampling techniques (e.g., SMOTE) for better class balance
Experiment with advanced ensemble models (XGBoost, LightGBM)
Deploy the model as a web application using Flask or Streamlit for real-time churn prediction
