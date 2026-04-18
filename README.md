🏋️ Body Performance Analytics & Intelligent Classification System
🔴 Overview

This project is part of a Machine Learning & Data Analysis project focused on predicting and analyzing human physical performance using body measurements and fitness indicators.

The main goals are:

Classify physical performance levels (A, B, C, D)
Predict explosive power using regression (broad jump)
Extract insights to understand fitness patterns
🎯 Objectives
Build a predictive system for fitness classification
Analyze relationships between body features and performance
Compare multiple machine learning models
Improve decision-making in sports and health analytics
Identify key factors affecting physical performance
🗂️ Dataset Design

The dataset contains 13,393 records (13,371 after cleaning) with 12 features.

🔑 Features:
Age
Gender
Height (cm)
Weight (kg)
Body Fat %
Blood Pressure (Systolic & Diastolic)
Grip Force
Sit-ups Count
Flexibility (Sit & Bend)
Broad Jump (cm)
Performance Class (A–D)
🔗 Key Relationships:
Strength features strongly impact performance
Body fat negatively affects athletic ability
Age has a declining effect on performance
Gender significantly influences results
🛠️ Technologies Used
Python 🐍
Pandas & NumPy
Scikit-learn
TensorFlow / Keras
Matplotlib & Seaborn
Machine Learning Algorithms
🧹 Data Cleaning & Preprocessing
Removed duplicates and invalid records
Detected unrealistic values (e.g., zero blood pressure)
Handled outliers and inconsistent data
Final dataset: 13,371 clean records
Ensured balanced classes across all categories
📊 Exploratory Data Analysis (EDA)

We explored the dataset to understand patterns and relationships:

Age distribution and its impact on performance
Correlation between strength and fitness level
Gender-based performance differences
Body fat influence on athletic ability
Feature relationships using correlation heatmaps
🔍 Key Insights
🧠 Gender is a strong predictor of performance
📉 Performance decreases with age
💪 Grip strength and sit-ups are highly important features
⚖️ Body fat negatively impacts performance
❤️ Blood pressure has very low correlation with fitness
🏃 Broad jump strongly reflects explosive power
🤖 Machine Learning Models
Classification Models:
K-Nearest Neighbors (KNN)
Decision Tree (Pruned & Unpruned)
Random Forest 🌲
Support Vector Machine (SVM)
Neural Network 🧠
🏆 Best Model:
Neural Network → 74.23% Accuracy
Model	Accuracy
Neural Network	⭐ 74.23%
Random Forest	72%
SVM	71.71%
Decision Tree	68%
KNN	62.77%
📈 Regression Model:
Linear Regression (OLS)

Performance:

R² Score ≈ 0.79
RMSE ≈ 18 cm
Key Findings:
Positive impact: grip force, sit-ups, height
Negative impact: age, body fat
📌 Project Pipeline
Data Collection
Data Cleaning
Exploratory Data Analysis
Feature Engineering
Model Training
Evaluation & Comparison
👥 Team Members
Nada Khaled Mahmoud (Team Leader)
Neama Eid Darwish
Fatima Youssef Kamal
Mona Yasser Abdelkader
Hagar Roshdy Ramadan
Nourhan Abdelkhaleq Abdelkhaleq
🚀 Future Work
Deploy as a web application
Improve deep learning accuracy
Add real-time fitness tracking
Extend dataset with more features
