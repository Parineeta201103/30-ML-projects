# 🌤️ Weather Forecasting Using Simple Linear Regression

## 📌 Project Overview

This project focuses on building a weather forecasting model using **Simple Linear Regression**, one of the most fundamental algorithms in machine learning. Using historical temperature data from various cities around the world, the goal is to predict the **Average Temperature** based on temporal features like the **day**, **month**, and **year**.

---

## 🧠 Problem Statement

Predict the **average daily temperature** using past weather data, with the aim of understanding how temperature trends change over time for a specific region.

---

## 🧾 Dataset Information

**Dataset Name:** City Temperature Dataset  
**Source:** [Kaggle]

### 📊 Features in the dataset include:

- `Region`: Geographical region of the city  
- `Country`: Name of the country  
- `State`: Name of the state (if applicable)  
- `City`: Name of the city  
- `Month`, `Day`, `Year`: Date information  
- `AvgTemperature`: Average temperature in Fahrenheit  

---

## 🧹 Data Preprocessing Steps

1. **Data Loading:** Loaded the dataset using `pandas`.
2. **City Selection:** Focused on a single city for simplicity.
3. **Missing/Invalid Data:**  
   - Removed rows where `AvgTemperature = -99` (which indicates missing/invalid entries).
4. **Feature Engineering:**  
   - Used `Month`, `Day`, and `Year` as features.
   - Target variable: `AvgTemperature`.
5. **Train-Test Split:**  
   - Split the dataset into training and testing sets using `train_test_split`.

---

## 📈 Model Building

### Algorithm Used: **Simple Linear Regression**

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
```

- **X (Features):** `Year`, `Month`, `Day`  
- **y (Target):** `AvgTemperature`

---

## 📊 Evaluation Metrics

- **Mean Squared Error (MSE)**  

These metrics help assess how well the model's predictions align with the actual values.

```python
from sklearn.metrics import mean_squared_error

mse = mean_squared_error(y_test, y_pred)

```

---

## 📉 Visualizations

- **Scatter plot** comparing actual vs predicted average temperature  
- **Regression line** over time showing trend  
- **Residual error distribution**

Visualizations were created using **Matplotlib** to help interpret the model performance intuitively.

---

## 📦 Libraries Used

- `pandas` – data manipulation  
- `numpy` – numerical operations  
- `matplotlib` – data visualization  
- `scikit-learn` – machine learning models and metrics  

---

## 📌 Key Learnings

- Built an end-to-end linear regression model on real-world time-series data  
- Understood preprocessing of noisy weather data  
- Interpreted regression coefficients and their impact  
- Evaluated the model using appropriate error metrics and visualization  

---

## 🚀 Future Scope

- Use additional features like humidity, wind speed, and weather conditions if available  
- Convert Fahrenheit to Celsius for broader understanding  
- Compare performance of Linear Regression with more complex models:
  - **Polynomial Regression**
  - **Random Forest Regressor**
  - **XGBoost**
- Deploy the model as an interactive dashboard or web app (e.g., using Streamlit)


