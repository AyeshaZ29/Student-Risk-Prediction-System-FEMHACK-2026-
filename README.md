Student Risk Prediction System
Overview

This project focuses on predicting student academic risk using machine learning techniques. The goal is to identify students who may be at low, medium, or high risk of poor performance or dropout at an early stage, allowing educators to take timely action. The system analyzes student engagement and demographic data and presents the results through a user-friendly Streamlit web application.

Dataset

The project uses the xAPI-Edu-Data.csv dataset, which contains student behavioral and academic information. Key features include:

Raised hands in class

Visited learning resources

Announcements viewed

Participation in discussions

Demographic and academic attributes (gender, nationality, semester, parental involvement, etc.)

The target variable is Class, which represents student performance levels:

H – High

M – Medium

L – Low

Exploratory Data Analysis (EDA)

EDA is performed to understand the structure and characteristics of the data. This includes:

Checking data types and missing values

Generating descriptive statistics

Visualizing numerical feature distributions using histograms

Analyzing categorical features using bar charts

Studying correlations between numerical features

Data Preprocessing

Before model training, the following preprocessing steps are applied:

Categorical variables are converted into numerical form using one-hot encoding

Numerical features are scaled using StandardScaler

The dataset is split into 80% training and 20% testing sets

Machine Learning Models

Three classification models are trained and evaluated:

Logistic Regression

Decision Tree Classifier

Random Forest Classifier

Model performance is compared using accuracy and classification reports. The Random Forest Classifier achieves the highest accuracy of approximately 84% and is selected as the final model.

Risk Score and Categorization

A risk score is calculated for each student as:

Risk Score = 1 − Probability of High Performance (H)

Based on this score, students are categorized into:

Low Risk (≤ 0.5)

Medium Risk (> 0.5 and ≤ 0.8)

High Risk (> 0.8)

Feature Importance

Feature importance is extracted from the Random Forest model to identify the most influential factors affecting student risk, such as:

Visited learning resources

Raised hands

Student absence days

Announcement views

Model Saving and Predictions

The trained model, scaler, and feature importance values are saved using joblib. A predictions.csv file is generated containing:

student_id

risk_score

risk_label (Low / Medium / High)

predicted_dropout (0 or 1)

Streamlit Application

A Streamlit web application (app.py) is developed to:

Upload student CSV data

Display top 20 high-risk students

Show individual student risk scores and labels

Explain key factors contributing to each student’s risk

Tools and Technologies

Python

Pandas, NumPy

Matplotlib, Seaborn

Scikit-learn

Streamlit

Conclusion

This project demonstrates how machine learning can be effectively used in education to identify at-risk students early. The system provides both predictive power and interpretability, making it a practical tool for academic decision-making and student support initiatives.
