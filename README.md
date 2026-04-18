🏋️ Body Performance Analytics & Intelligent Classification System
📌 Project Overview

This project focuses on analyzing physical fitness data and building machine learning models to evaluate and predict human body performance.

The system performs two main tasks:

Classification: Predict performance level (A, B, C, D)
Regression: Predict broad_jump_cm as a measure of explosive power

The project is designed for applications in:

Fitness assessment
Sports science
Health monitoring systems
📊 Dataset Description

The dataset contains 13,393 records with features related to:

Anthropometric data (height, weight, body fat)
Physiological data (blood pressure)
Performance metrics (grip strength, sit-ups, flexibility, jump distance)
🔑 Features include:
age, gender
height_cm, weight_kg
body_fat_percent
systolic, diastolic
gripForce
sit_and_bend_forward_cm
sit_ups_counts
broad_jump_cm
class (Target: A–D)
🧹 Data Cleaning & Preprocessing
Removed duplicates and invalid records
Detected and removed biologically impossible values (e.g., zero blood pressure)
Final dataset: 13,371 clean records
Dataset is perfectly balanced across classes
🔍 Exploratory Data Analysis (EDA)

Key insights:

📉 Performance decreases with age
💪 Strong correlation between strength metrics (grip force, sit-ups, jump)
⚖️ Body fat negatively impacts performance
🚻 Gender is a strong predictor
❤️ Blood pressure has negligible impact
🤖 Machine Learning Models
🔹 Classification Models
K-Nearest Neighbors (KNN)
Decision Tree (Pruned & Unpruned)
Random Forest
Support Vector Machine (SVM)
Neural Network (MLP)
🏆 Best Model:
Neural Network → 74.23% Accuracy
Model	Accuracy
Neural Network	74.23%
Random Forest	72%
SVM	71.71%
Decision Tree	68%
KNN	62.77%
🔹 Regression Model
Linear Regression (OLS)

📈 Performance:

R² Score ≈ 0.79
RMSE ≈ 18 cm

📊 Key factors affecting jump:

Positive: grip strength, sit-ups, height
Negative: age, body fat
⚙️ Project Pipeline
Data Cleaning
Exploratory Data Analysis
Feature Engineering
Model Training
Evaluation & Comparison
🧠 Technologies Used
Python 🐍
Pandas & NumPy
Matplotlib & Seaborn
Scikit-learn
TensorFlow / Keras
👥 Team Members
Nada Khaled Mahmoud (Team Leader)
Neama Eid Darwish
Fatima Youssef Kamal
Mona Yasser Abdelkader
Hagar Roshdy Ramadan
Nourhan Abdelkhaleq
🎯 Conclusion

This project demonstrates how machine learning can effectively analyze physical performance and provide accurate predictions for both classification and regression tasks.

📎 Future Work
Improve model performance using advanced deep learning
Deploy as a web or mobile application
Integrate real-time fitness tracking data
