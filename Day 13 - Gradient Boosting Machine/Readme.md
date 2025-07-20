# 🛫 Flight Customer Satisfaction Prediction using Gradient Boosting Machine (GBM)

## 📝 Overview
This project aims to predict whether airline passengers are **satisfied or not** with their flight experience based on various customer features using **Gradient Boosting Machine (GBM)** – a robust and powerful ensemble learning algorithm. It is a **binary classification problem**, with the goal of assisting airlines in identifying key drivers of customer satisfaction and improving their services.

## 📁 Dataset Description
The dataset includes customer profiles, flight-related attributes, and service ratings. It is pre-split into:
- `train.csv`: Used to train the model
- `test.csv`: Used to evaluate the model

### 🎯 Target Variable
- `satisfaction`: Categorical feature with values:
  - `satisfied`
  - `neutral or dissatisfied`  
  (Converted to binary: `1` for satisfied, `0` for not satisfied)

## 🧪 Project Pipeline

### 🔹 Step 1: Import Libraries
```python
import pandas as pd                # Data manipulation
import numpy as np                 # Numerical operations
import matplotlib.pyplot as plt    # Visualization
```

### 🔹 Step 2: Load the Dataset
```python
train = pd.read_csv("train.csv")
test = pd.read_csv("test.csv")
```

### 🔹 Step 3: Data Inspection
```python
train.head()
test.head()
```

### 🔹 Step 4: Handle Missing Values
```python
train = train.dropna()
test = test.dropna()
```

### 🔹 Step 5: Encode Categorical Features
```python
train_encoded = pd.get_dummies(train, drop_first=True)
test_encoded = pd.get_dummies(test, drop_first=True)
```

### 🔹 Step 6: Split Features and Target
```python
y_train = train_encoded['satisfaction_satisfied'].map({True:1, False:0})
X_train = train_encoded.drop(columns='satisfaction_satisfied')
y_test = test_encoded['satisfaction_satisfied'].map({True:1, False:0})
X_test = test_encoded.drop(columns='satisfaction_satisfied')
```

### 🔹 Step 7: Model Building - GBM
```python
from sklearn.ensemble import GradientBoostingClassifier
model = GradientBoostingClassifier(random_state=42)
model.fit(X_train, y_train)
```

### 🔹 Step 8: Prediction
```python
y_pred = model.predict(X_test)
```

### 🔹 Step 9: Evaluation
```python
from sklearn.metrics import accuracy_score, confusion_matrix
print("Accuracy:", accuracy_score(y_pred, y_test))
print("Confusion Matrix:\n", confusion_matrix(y_pred, y_test))
```

### 🔹 Step 10: Feature Importance Visualization
```python
feature_importance = model.feature_importances_
sorted_index = np.argsort(feature_importance)
plt.figure(figsize=(10, 10))
plt.barh(X_train.columns[sorted_index], feature_importance[sorted_index], color='Teal')
plt.xlabel("Importance")
plt.title("Feature Importance")
plt.show()
```

## 📊 Model Results
- ✅ Accuracy: **XX%**
- ✅ Confusion Matrix:
```
[[TN  FP]
 [FN  TP]]
```
- ✅ Most important features:
  - Inflight entertainment
  - Seat comfort
  - Onboard service
  - Leg room service
  - Departure/Arrival time convenient

## 📌 Key Insights
- High scores for in-flight entertainment, seat comfort, and service quality are strong indicators of satisfaction.
- Delays, poor food, or cramped space are major contributors to dissatisfaction.
- Feature importance plots can guide airlines on which services to improve for better retention.

## 💡 Future Enhancements
- Tune hyperparameters using GridSearchCV or RandomizedSearchCV
- Handle class imbalance using SMOTE if necessary
- Try more advanced models: XGBoost, LightGBM, CatBoost
- Use SHAP values for model explainability

## 🛠️ Tech Stack
- Python (pandas, numpy, matplotlib, scikit-learn)
- Jupyter Notebook / VSCode
- Supervised Machine Learning
- Gradient Boosting (from sklearn)

## 📂 File Structure
```
📦 flight_satisfaction_gbm/
├── train.csv
├── test.csv
├── model.ipynb / model.py
├── feature_importance.png
└── README.md
```
