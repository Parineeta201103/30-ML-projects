## 🌿 Day 14 – CO₂ Emissions Prediction Using Vehicle Data (Canada)

This project focuses on building regression models to predict vehicle CO₂ emissions (g/km) using specifications of cars sold in Canada. The goal is to understand how different attributes like engine size, fuel consumption, and vehicle type influence carbon output.

### 📘 Dataset Overview
- Source: Kaggle - CO2 Emissions_Canada.csv
- Records: 7385 vehicle entries
- Features: 12 columns, including both categorical (e.g., fuel type) and numerical (e.g., engine size) variables
- Target Variable: CO2 Emissions(g/km) – The average grams of carbon dioxide emitted per kilometer by a vehicle

### 🧠 What Is Regression?
Regression is a supervised learning technique used to predict continuous numerical values. In this case, we use it to predict CO₂ emissions based on vehicle features.

### 🔄 Workflow Breakdown

1. **Data Loading and Inspection**
- Used pandas to read the CSV file and explore data using .info(), .describe(), .isnull().sum()
- No missing values were found
- Identified categorical and numerical columns
- Checked for high-cardinality features (Model had 2053 unique entries and was dropped)

2. **Exploratory Data Analysis (EDA)**
EDA helps uncover patterns, correlations, and outliers before modeling.
- Correlation heatmap: Showed strong positive correlation between engine size, fuel consumption, and CO₂ emissions
- Scatter plot: Visualized Engine Size (L) vs CO₂ Emissions(g/km)
- Box plot: Showed fuel type influence on emissions
- Pair plot: Compared relationships between multiple numerical features

Why EDA? To visualize relationships, detect collinearity, and generate hypotheses about which features may be important.

3. **Data Preprocessing**
- Dropped columns: Make, Model (not predictive and high-cardinality)
- Applied One-Hot Encoding to categorical features: Vehicle Class, Fuel Type, Transmission
- Split the dataset into:
  - Features (X): All columns except CO2 Emissions
  - Target (y): The CO2 Emissions(g/km) column

Why One-Hot Encoding? ML models can't interpret text, so we convert categorical variables into binary flags.

4. **Model Training and Evaluation**

Linear Regression:
Linear regression attempts to fit a straight line (or hyperplane) that minimizes the error between predicted and actual values.

model = LinearRegression()
model.fit(X_train, y_train)

- R² Score: 0.932 → 93.2% of the variance in CO₂ emissions is explained by the model.
- RMSE: 13.36 g/km → Average prediction error is ~13.36 grams of CO₂ per km.

5. **Regularization Techniques**

Ridge Regression:
Adds L2 penalty to the loss function to shrink coefficients — helps prevent overfitting when features are highly correlated.
- R² Score: 0.932
- RMSE: 13.36

Lasso Regression:
Adds L1 penalty, which can shrink some coefficients to exactly zero, effectively performing feature selection.
- R² Score: 0.932
- RMSE: 13.36
- Number of features set to zero: (varies based on data)

Why Regularize? To improve generalization and reduce model complexity, especially with many predictors or dummy variables.

6. **Feature Importance (Lasso Coefficients)**
Lasso regression provides insights into which features are most predictive by examining which ones retain non-zero coefficients.

lasso_coeffs = pd.Series(lasso.coef_, index=X.columns)

### ✅ Final Results Summary

| Model              | R² Score | RMSE (g/km) |
|-------------------|----------|-------------|
| Linear Regression | 0.932    | 13.36       |
| Ridge Regression  | 0.932    | 13.36       |
| Lasso Regression  | 0.932    | 13.36       |

### 🔍 Key Takeaways
- All models performed equally well due to the clean and structured nature of the dataset.
- Strong linear relationships made simple models highly effective.
- Lasso Regression provided feature selection and interpretability benefits.
- Real-world datasets are often noisier, so achieving R² ≈ 0.99 like in cleaner datasets is uncommon.

### 🚀 Future Enhancements
- Hyperparameter tuning using GridSearchCV for Ridge/Lasso
- Try Random Forest or XGBoost for non-linear relationships
- Apply the pipeline to a real-world, messier dataset like life expectancy, loan prediction, or product failure

📁 Files included:
- CO2_Emissions_Canada.csv


