# 🏋️ Body Performance Analytics & Intelligent Classification System  

![Python](https://img.shields.io/badge/Python-3.x-blue)  
![ML](https://img.shields.io/badge/Machine%20Learning-Project-green)  
![Status](https://img.shields.io/badge/Status-Completed-success)  

---

## 📑 Table of Contents  
- [📌 Overview](#-overview)  
- [🎯 Objectives](#-objectives)  
- [📊 Dataset](#-dataset-description)  
- [🧹 Data Preprocessing](#-data-preprocessing)  
- [📈 EDA](#-exploratory-data-analysis-eda)  
- [🤖 Models](#-machine-learning-models-used)  
- [🏆 Performance](#-model-performance)  
- [📉 Regression](#-regression-results)  
- [⚙️ Technologies](#️-technologies--tools)  
- [🔄 Pipeline](#-project-pipeline)  
- [🚀 Applications](#-applications)  

---

## 📌 Overview  
This project focuses on analyzing physical fitness data and building intelligent machine learning models to evaluate human body performance.  

The system aims to:  
- Classify individuals into fitness levels (A, B, C, D)  
- Predict physical performance using regression models  
---

## 🎯 Objectives  
- Build a classification system to predict fitness level:  
  - A (Excellent)  
  - B (Good)  
  - C (Average)  
  - D (Poor)  

- Build a regression model to predict:  
  - `broad_jump_cm` (indicator of explosive power)  

- Compare multiple machine learning models and evaluate their performance  

---

## 📊 Dataset Description  
The dataset contains body measurements and fitness indicators, including:  

- Age, Gender  
- Height & Weight  
- Body Fat %  
- Blood Pressure (Systolic & Diastolic)  
- Grip Strength  
- Flexibility  
- Sit-ups Count  
- Broad Jump Distance  

After cleaning:  

- ✅ 13,371 records  
- ✅ Balanced classes (~25% each)  

---

## 🧹 Data Preprocessing  
- Removed duplicates  
- Removed biologically impossible values (e.g., zero blood pressure)  
- Handled hidden invalid data  
- Ensured high data integrity  

---

## 📈 Exploratory Data Analysis (EDA)  

### 🔍 Key Insights  
- 📉 Performance decreases with age  
- 💪 Strong positive correlation:  
  - Grip Strength ↔ Broad Jump  
  - Sit-ups ↔ Broad Jump  
- ⚠️ Body fat negatively impacts performance  
- 🚫 Blood pressure has negligible effect  
- 👥 Gender is a strong predictor  

---

## 🤖 Machine Learning Models Used  

### 🔹 Classification Models  
- K-Nearest Neighbors (KNN)  
- Decision Tree  
- Random Forest  
- Support Vector Machine (SVM)  
- Neural Network (MLP)  

### 🔹 Regression Model  
- Linear Regression (OLS)  

---

## 🏆 Model Performance  

| Model | Accuracy |
|------|--------|
| Neural Network | **74.23% (Best)** |
| Random Forest | 72% |
| SVM | 71.7% |
| Decision Tree | 68% |
| KNN | 62.7% |

📌 **Best Model:** Neural Network  

---

## 📉 Regression Results  

- **Target:** `broad_jump_cm`  
- **R² Score:** ~ 0.79  
- **RMSE:** ~ 18 cm  

### 🔑 Key Influencing Features  

**Positive Impact:**  
- Sit-ups  
- Grip strength  
- Gender  

**Negative Impact:**  
- Age  
- Body fat  

---

## ⚙️ Technologies & Tools  
- Python 🐍  
- Pandas & NumPy  
- Matplotlib & Seaborn  
- Scikit-learn  
- TensorFlow / Keras  
- Google Colab  

---

## 🔄 Project Pipeline  
- Data Cleaning  
- Data Exploration  
- Feature Engineering  
- Model Training  
- Model Evaluation  
- Comparison & Insights  

---

## 🚀 Applications  
- Fitness assessment systems  
- Sports science analysis  
- Health monitoring tools  
- Personalized training recommendations  

---

## 🤝 Connect With Me
Feel free to connect or reach out for feedback!
<p align="center">
  <a href="mailto:nadakhaledmahmoud412@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-Contact_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>

  <a href="https://www.linkedin.com/in/nada-khaled-rashad/">
    <img src="https://img.shields.io/badge/LinkedIn-Lets_Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
</p>


---
