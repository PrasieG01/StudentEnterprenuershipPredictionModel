# StudentEnterprenuershipPredictionModel

##Project Overview
This project aimed to build a Machine Learning model to predict whether a university student would start a business based on their demographics, academic performance, and psychometric traits (e.g., Self-Reliance, Risk-Taking). The dataset consists of approximately 7,300 student records.

##Methods and Workflow
###Data Cleaning & Preprocessing
Target Handling: Dropped rows where the target variable (StartedBusiness) was missing to ensure ground-truth training data.

###Imputation:

Used SimpleImputer(strategy='mean') for numeric features (Age, GPA, Personality Scores).

Used SimpleImputer(strategy='most_frequent') for categorical features (Major, Gender).

Encoding: Applied One-Hot Encoding (pd.get_dummies) to convert categorical variables into machine-readable numeric formats.

##Using two models

Model 1: Decision Tree Classifier
Goal: Establish a baseline model.

Outcome: The single tree was prone to overfitting. While accuracy appeared high, it struggled to generalize to new data and failed to capture the minority class (Entrepreneurs).

Model 2: Random Forest Model with UnderSampling

Solution: To fix the bias, I implemented Random Undersampling. I randomly removed examples from the majority class ("No") until I had a perfectly balanced 50/50 dataset.

##Results & Analysis
This forced the model to stop "cheating" based on class frequency and look for actual patterns in the data.

After balancing the data to ensure a fair test, the Random Forest converged on the following metrics:

Accuracy: ~50%

Precision/Recall: ~0.50

###Key Takeaway: The "Null Result"
The model's performance (equivalent to a coin flip) demonstrates that in this specific dataset, there is no statistical difference between students who start businesses and those who do not.

This analysis effectively debunks the "Entrepreneurial Stereotype" for this population. It indicates that internal traits like GPA, Major, or self-reported "Risk-Taking" scores have zero predictive power regarding entrepreneurship. Success is likely driven by external factors not captured in this survey.
