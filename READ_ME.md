# 📌 Loan Default Prediction

## 📖 Project Overview
The goal of this project is to analyze loan applicant data and build predictive features for loan default classification.  
This repository contains **exploratory data analysis (EDA)** and **feature engineering** steps to prepare the dataset for modeling
and then perform the model building and evaluation procedure.

---

## 🔍 Data Understanding & Cleaning
1. **Null Values**  
   - Verified that there were **no missing values** in the dataset.  

2. **Data Inconsistency & Inappropriate Values**  
   - Checked all features for outliers, negative values, or unrealistic entries.  
   - No major inconsistencies found.  

3. **Dropped Irrelevant Columns**  
   - Removed `Loan_ID` column since it carried no predictive value.  

4. **Duplicate Records**  
   - Checked for duplicate rows to avoid data leakage or bias.  

---

## 📊 Exploratory Data Analysis (EDA)
### 1. **Univariate Analysis**
   - Distribution plots for numerical features (e.g., Age, LoanAmount, ApplicantIncome).  
   - Count plots for categorical variables (e.g., Gender, Education, Employment Type).  

### 2. **Bivariate Analysis**
   - Relationship of each feature with **Loan Default** target variable.  
   - Visualizations (boxplots, bar charts, and correlation plots) included in the notebook.  


## 🛠️ Feature Engineering
Created new meaningful features to improve model predictive power and then shown there distributions by using plots:

- **LTI (Loan-to-Income Ratio):** LoanAmount / Income
- **EMI (Equated Monthly Installment):** LoanAmount / Loan_Term 
- **Disposable Income:** Income − EMI
- **Credit Line Utilization:** LoanAmount / Number_of_Credit_Lines 

These engineered features capture applicant’s **financial stress** and **repayment capacity**, which are crucial for loan default prediction. 

## 🤖 Models Trained
Several algorithms were tested to benchmark performance:

- Logistic Regression (baseline model)  
- Random Forest Classifier  
- Gradient Boosting Classifier  
- AdaBoost Classifier  
- XGBoost Classifier    

---

## ⚙️ Hyperparameter Tuning
- Grid Search and Randomized Search were applied on selected models.  
- XGBoost tuning included parameters like:
    -subsample
    -reg_lambda
    -reg_alpha
    -n_estimators
    -min_child_weight
    -max_depth
    -learning_rate
    -gamma
    -colsample_bytree


- Optuna (Bayesian optimization) was also explored for automated hyperparameter tuning.  

---

## 📈 Evaluation Metrics
Models were evaluated using:

- **ROC-AUC Score** (main metric)    
- Recall, classification matrix
- Confusion Matrix  

---

## 🔎 Key Results
- Training AUC ≈ **0.91–0.92**  
- Validation/Test AUC ≈ **0.74–0.75**  
- Clear **overfitting trend** observed (gap between train and test).
- Despite tuning and resampling, performance plateaued around 0.75 AUC on test data.

---

## Purpose
This project demonstrates that machine learning is not just about calling `fit()` and `predict()`. 
It involves careful consideration of data quality, feature engineering, feature selection, model 
choice, and hyperparameter tuning. For full explanation see purpose.txt.




