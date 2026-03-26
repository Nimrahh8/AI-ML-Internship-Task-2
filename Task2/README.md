# Telecom Customer Churn Prediction

## Problem Statement & Objective

### Problem Statement
Customer churn is a major concern for telecom companies. The goal is to predict whether a customer will leave (churn) based on their usage and demographic data.

### Objectives
- Build a machine learning model to predict customer churn
- Perform data preprocessing and feature engineering
- Train and compare multiple models (Logistic Regression, Random Forest)
- Optimize models using hyperparameter tuning
- Evaluate performance using Accuracy, Precision, Recall, F1-score, and ROC-AUC
- Provide actionable insights for business decision-making

---

## Dataset Used
- **Dataset:** Telco Customer Churn (IBM Sample Dataset)  
- **Source:** [Telco Customer Churn CSV](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)  
- **Rows:** ~7,000  
- **Features:** 20+ features including demographic info, services subscribed, and billing info  
- **Target:** `Churn` (Yes/No)

---

## Models Applied
- **Logistic Regression**
- **Random Forest Classifier**
- **Preprocessing:**  
  - Numerical features → median imputation + StandardScaler  
  - Categorical features → most frequent imputation + OneHotEncoding  
  - Handled class imbalance with class weights
- **Hyperparameter Tuning:** GridSearchCV with StratifiedKFold
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-score, ROC-AUC
- **Feature Importance:** Extracted from Random Forest

---

## Key Results and Findings

### Model Performance
| Model                       | Accuracy | Precision | Recall | F1    | ROC-AUC |
|------------------------------|---------|-----------|--------|-------|---------|
| Logistic Regression (Baseline)| 0.79    | 0.63      | 0.51   | 0.57  | 0.79    |
| Logistic Regression (Tuned)   | 0.81    | 0.65      | 0.54   | 0.59  | 0.81    |
| Random Forest (Baseline)      | 0.81    | 0.66      | 0.56   | 0.61  | 0.83    |
| Random Forest (Tuned)         | 0.83    | 0.69      | 0.58   | 0.63  | 0.85    |

### Feature Importance (Top Features from Random Forest)
- Tenure  
- Contract type  
- Monthly charges  
- Payment method  
- Total charges  

### Business Insights
- Customers with short tenure are more likely to churn  
- Month-to-month contracts have higher churn risk  
- Higher monthly charges correlate with churn  

### Limitations
- Imbalanced target variable; class weighting used as mitigation  
- Models could be further improved with ensemble methods (XGBoost, LightGBM)  

### Future Improvements
- Use SMOTE or other oversampling techniques for better imbalance handling  
- Explore more advanced models like XGBoost or LightGBM  
- Deploy as a web application using Flask or Streamlit for real-time predictions  
