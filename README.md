🏋️ Body Performance Analytics & Intelligent Classification System






📑 Table of Contents
📌 Overview
🎯 Objectives
🗂️ Dataset
🔗 Tasks
🛠️ Technologies
🧹 Data Cleaning
📊 EDA
📈 Key Insights
🤖 Models
🏆 Best Model
📉 Regression
📊 Evaluation
🧠 Learnings
🚀 Conclusion
🙌 Team
📌 Overview

This project analyzes body performance data using Machine Learning techniques to classify fitness levels and predict athletic performance.

It supports applications in:

Fitness assessment
Sports analytics
Health monitoring
🎯 Objectives
Classify performance levels (A, B, C, D)
Predict broad jump using regression
Analyze relationships between body metrics
Extract meaningful insights from data
🗂️ Dataset

The dataset includes:

Age, Gender
Height, Weight
Body Fat %
Blood Pressure
Grip Strength
Flexibility
Sit-ups Count
Broad Jump
Performance Class
🔗 Tasks
🧠 Classification → Predict performance class
📉 Regression → Predict broad_jump_cm
🛠️ Technologies
Python
Pandas & NumPy
Matplotlib & Seaborn
Scikit-learn
🧹 Data Cleaning
Removed duplicates
Fixed invalid values
Removed impossible measurements
Handled hidden missing values

✅ Final dataset: 13,371 rows

📊 EDA
Distribution analysis
Correlation heatmap
Boxplots
Gender & age analysis
Performance trends
📈 Key Insights
💪 Strong link: Grip strength ↔ Broad jump
📉 Body fat negatively affects performance
📊 Performance decreases with age
🚹 Gender is a strong predictor
❌ Blood pressure has no significant impact
🤖 Models
Model	Accuracy
KNN	62%
Decision Tree	68%
Random Forest	72%
SVM	71.7%
Neural Network	74.23%
🏆 Best Model

👉 Neural Network (MLP) achieved the best performance

📉 Regression

Model: Linear Regression

R² Score ≈ 0.79
RMSE ≈ 18
📊 Evaluation
Train/Test splits
Cross-validation
Accuracy, Precision, Recall, F1
RMSE & R²
🧠 Learnings
Data cleaning is critical
Feature relationships matter
Model tuning improves performance
Real-world data is complex
🚀 Conclusion

Machine Learning can effectively:

Classify fitness levels
Predict athletic performance
Support health & sports decisions
🙌 Team
Nada Khaled Mahmoud
Neama Eid Darwish
Fatima Youssef Kamal
Mona Yasser Abdelkader
Hagar Roshdy Ramadan
Nourhan Abdelkhaleq Abdelkhaleq
⭐ Don't forget
