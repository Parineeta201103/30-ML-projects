# 📘 Day 15 – Life Expectancy Prediction using Machine Learning

This project aims to **predict the life expectancy** of a country based on multiple **demographic, health, economic, and social factors** using various regression algorithms. The primary objective is not just to build a highly accurate model, but also to understand the **relationships between variables**, compare **different modeling strategies**, and justify each step with statistical and machine learning theory.

---

## 📁 Dataset Overview

- **Source**: Kaggle – [Life Expectancy (WHO)](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who)
- **Rows**: 2938
- **Columns**: 22
- **Years Covered**: 2000 to 2015
- **Attributes**:
  - **Target Variable**: `Life expectancy`
  - **Predictors** include:
    - Health indicators (e.g., `HIV/AIDS`, `BMI`, `Hepatitis B`)
    - Economic indicators (`GDP`, `Total expenditure`)
    - Social factors (`Schooling`, `Status`, `Alcohol`)
    - Mortality statistics (`infant deaths`, `adult mortality`, `under-five deaths`)

---

## 🎯 Problem Statement

> Build a regression model that accurately predicts **Life Expectancy (in years)** of a country using relevant global health and development indicators.

---

## 📊 Definitions of Key Concepts

### 🧮 Life Expectancy
The average number of years a newborn is expected to live, assuming mortality patterns at the time of birth remain constant.

### 🔢 Regression
A supervised learning technique used to predict **continuous numerical outcomes** based on one or more independent variables.

### 📉 R² Score (Coefficient of Determination)
Indicates the proportion of variance in the dependent variable that is predictable from the independent variables.  
- Ranges from 0 to 1; higher is better.

### 🔍 RMSE (Root Mean Squared Error)
A metric that calculates the square root of the average squared difference between predicted and actual values.  
- Lower RMSE indicates better prediction accuracy.

---

## 🔍 Exploratory Data Analysis (EDA)

### 🧠 Key Positive Correlations with Life Expectancy:
| Feature                          | Correlation |
|----------------------------------|-------------|
| `Schooling`                      | +0.717      |
| `Income composition of resources`| +0.689      |
| `BMI`                            | +0.559      |
| `Status`                         | +0.482      |
| `GDP`, `Alcohol`, `Polio`        | +0.39–0.45  |

### 🚫 Key Negative Correlations:
| Feature               | Correlation |
|-----------------------|-------------|
| `Adult Mortality`     | –0.696      |
| `HIV/AIDS`            | –0.557      |
| `Thinness`, `Deaths`  | –0.45 to –0.20 |

These patterns support real-world medical evidence, where better education, healthcare, and wealth improve life expectancy.

---

## 🛠️ Data Preprocessing

- **Missing Values**: Handled using mean/mode imputation
- **Categorical Encoding**:
  - `Status`: One-hot encoded as 1 (Developed) and 0 (Developing)
- **Dropped**:
  - `Country`: Categorical and not directly predictive
- **Feature Scaling**: Not required for tree-based models

---

## 🤖 Models Used and Evaluated

| Model               | Definition | R² Score | RMSE |
|--------------------|------------|----------|------|
| **Linear Regression** | Assumes a linear relationship between independent and dependent variables | 0.809 | 4.06 |
| **Ridge Regression**  | Adds L2 penalty to linear regression to reduce overfitting | 0.809 | 4.06 |
| **Lasso Regression**  | Adds L1 penalty, also performs feature selection | 0.800 | 4.16 |
| **Random Forest**      | An ensemble of decision trees built using bagging | **0.964** | **1.78** |

---

## 🌲 What is Random Forest?

> A **Random Forest** is an ensemble learning method that constructs multiple decision trees during training and outputs the mean prediction of the individual trees.

### ✅ Advantages:
- Handles **non-linear relationships** automatically
- **Robust to outliers** and missing data
- Doesn’t require **feature scaling**
- Provides **feature importance**
- Reduces overfitting by averaging many trees

### ✅ Cross-Validation Results:
- 5-Fold CV R² Scores: `[0.940, 0.886, 0.918, 0.918, 0.908]`
- **Mean CV R²**: `0.914`
- → Indicates **excellent generalization**

---

## 📉 Why Not Other Models?

### ❌ Decision Tree Regressor
- High variance
- Prone to overfitting on continuous targets
- Random Forest overcomes these issues by averaging many trees

### ❌ Support Vector Regression (SVR)
- Requires **feature scaling**
- Poor scalability for datasets > 1000 rows
- No natural feature importance
- Not ideal for interpretability

### ❌ XGBoost
- Would have been strong, but:
  - More complex tuning
  - Random Forest already gave **excellent performance**
  - Not necessary for this challenge scope

### ❌ Neural Networks
- Overkill for tabular data of this size
- High computation cost
- Lacks interpretability — which is important in healthcare

---

## ❓Why No Hyperparameter Tuning?

### What is Hyperparameter Tuning?
> It refers to searching the best combination of model parameters (e.g., number of trees, depth, learning rate) to improve model performance.

### Why I Skipped It:
- Even with **default settings**, Random Forest gave:
  - R² = 0.964, RMSE = 1.78
- CV confirmed stability → No signs of overfitting
- Focus of this challenge: **building and interpreting models efficiently**
- Tuning is best reserved for **production-scale pipelines**

---

## 📌 Feature Importance (Random Forest Output)

Top influential features in predicting life expectancy:

| Rank | Feature                            |
|------|------------------------------------|
| 1    | `Schooling`                        |
| 2    | `Adult Mortality`                  |
| 3    | `Income composition of resources`  |
| 4    | `HIV/AIDS`                         |
| 5    | `BMI`                              |
| 6    | `GDP`, `Polio`, `Diphtheria`       |

These insights match real-world determinants of global health outcomes.

---

## 🧠 Key Learnings

- Regression performance depends heavily on **feature selection** and **data quality**
- Tree-based models like Random Forest can outperform linear models when relationships are **non-linear and complex**
- Understanding **why not to use certain models** is as important as knowing which one to choose
- **Cross-validation** ensures model robustness and prevents overfitting
- In real-world applications, interpretability and explainability are crucial, especially in public health domains

---

## 🚀 Future Enhancements

- Add **XGBoost** with hyperparameter tuning
- Deploy a **Streamlit dashboard** to interactively explore predictions
- Perform **feature drift analysis** across years to understand temporal changes

---

## 🧾 Conclusion

This project demonstrates that Random Forest is a highly effective and interpretable model for predicting life expectancy using multi-domain indicators. While simpler models provide baseline understanding, ensemble methods provide the power and robustness needed for real-world insights.

---

