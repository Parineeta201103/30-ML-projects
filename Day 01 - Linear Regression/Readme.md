# 🏡 House Price Prediction Using Simple Linear Regression

## 📌 Project Overview

This project aims to predict the **median house value** in California districts using **Simple Linear Regression**, based on just one input feature — the **median income of households**. The objective is to understand how income levels influence housing prices using a transparent, interpretable model.

---

## 📊 Problem Statement

Housing prices are influenced by many socio-economic factors, one of the most important being household income. In this project, we build a model that attempts to predict house prices based solely on **median income (`MedInc`)**, to explore the strength of this relationship.

This is framed as a **regression problem**, where:

- **Input Feature (X)**: Median Income of households in the block
- **Target Variable (y)**: Median House Value in the block

---

## 📚 About the Dataset

We use the **California Housing Dataset** provided by the `scikit-learn` library. This dataset includes information collected from the 1990 U.S. Census and contains features for 20,000+ California districts.

### Key Features in the Dataset (only one used here):
- **MedInc**: Median income in the block group (used as the predictor)
- **MedHouseVal**: Median house value in the block group (used as the target)

---

## 🧠 Why Simple Linear Regression?

**Simple Linear Regression** is a foundational algorithm in machine learning used to predict a continuous target variable from a single input feature. It assumes a linear relationship between the input and the target, modeled as:

\[
y = \beta_0 + \beta_1 x + \epsilon
\]

Where:
- \( y \): Predicted house price
- \( x \): Median income
- \( \beta_0 \): Intercept (bias)
- \( \beta_1 \): Slope (effect of income on price)
- \( \epsilon \): Error term

This model is chosen for its **simplicity, interpretability, and clarity**, especially when exploring relationships between two variables.

---

## 🧪 Methodology

1. **Data Preparation**:
   - Load the dataset and extract only the relevant columns (`MedInc`, `MedHouseVal`).
   - Split the dataset into training and validation sets (80/20 ratio).

2. **Model Training**:
   - Fit a Simple Linear Regression model on the training data.
   - The model learns the best-fit line by minimizing the **Mean Squared Error (MSE)**.

3. **Model Evaluation**:
   - Make predictions on the validation data.
   - Evaluate the model using **Root Mean Squared Error (RMSE)**.

---

## 📏 Evaluation Metric: RMSE

- **Root Mean Squared Error (RMSE)** measures the average deviation between predicted and actual house prices.
- It is given by:

\[
\text{RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}
\]

Where:
- \( y_i \): Actual values
- \( \hat{y}_i \): Predicted values
- \( n \): Number of observations

✅ **Why RMSE?**
- RMSE penalizes larger errors more than smaller ones.
- It retains the same unit as the target variable (house prices), making it easy to interpret.

> In this project, the model achieved an RMSE of approximately **0.84**, which suggests that the model can estimate the median house value with a moderate level of error using just median income.

---

## 📈 Key Insights

- There is a **positive linear relationship** between household income and housing price — as income increases, house prices also tend to rise.
- While this model gives a baseline understanding, using only one feature limits its predictive power.
- Real-world housing prediction would benefit from **multiple regression** with additional features like location, house age, population density, etc.

---

## 💡 Future Scope

- Extend the model to **Multiple Linear Regression** using more features.
- Apply **Polynomial Regression** to capture non-linear patterns.
- Use **cross-validation** for more robust evaluation.
- Visualize residuals to detect heteroscedasticity or outliers.

---
