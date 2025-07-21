# 📱 Nomophobia and Mental Health Severity Prediction

## 🧠 Objective

This project aims to build **binary classification models** that predict the presence of:
- Anxiety
- Depression
- Sleep Quality Issues

using **behavioral** and **demographic features** linked to **mobile phone addiction (nomophobia)**. The project avoids data leakage by excluding questionnaire-based features used to derive the target variables.

---

## 📂 Dataset Overview

- **Target Variables**:
  - `anxiety_severity` (0 = No, 1 = Yes)
  - `depression_severity` (0 = No, 1 = Yes)
  - `sleep_quality_severity` (0 = No, 1 = Yes)

- **Input Features**:
  - Demographic: Age, Gender, Education, etc.
  - Behavioral: Screen time, pickups, bedtime, morning usage, fear of disconnection

- **Excluded Columns**:
  - `aq1–aq10`, `dq1–dq15`, `sq1–sq9` (used only to define target variables)

---

## 🔧 Preprocessing Steps

1. **Data Cleaning**
   - Removed IDs, timestamps, and questionnaire-based items

2. **Handling Missing Values**
   - Numerical: Imputed using mean
   - Categorical: Imputed using mode

3. **Encoding**
   - Used `pd.get_dummies(drop_first=True)` for categorical variables

4. **Feature Scaling**
   - Applied `StandardScaler` only for models like logistic regression/SVM

5. **Class Imbalance**
   - Addressed using **SMOTETomek** (from `imblearn.combine`) to handle imbalance in binary labels

---

## 🤖 Modeling

Separate models were trained for each target variable:

| Target Variable         | Best Model       | Accuracy | Resampling |
|-------------------------|------------------|----------|------------|
| Anxiety Severity        | XGBoost          | 90%      | SMOTETomek |
| Depression Severity     | Random Forest    | 88%      | SMOTETomek |
| Sleep Quality Severity  | Random Forest    | 80%      | SMOTETomek |

- Evaluated using:
  - Accuracy
  - F1-score
  - Confusion Matrix
  - Cross-validation (optional for stability)

---

## 🔍 Key Features Identified

Top contributing features across models:
- Daily screen time
- Late-night phone use / bedtime
- Number of daily pickups
- Morning phone checking
- Fear of losing signal / low battery panic
- Sleep delay due to phone

---

## ⚠️ Challenges

- **Class imbalance** in target variables
- Avoiding **data leakage** from questionnaire-derived scores
- Ensuring models remain interpretable and generalizable

---

## ✅ Next Steps

- Try **Ordinal Classification** for severity levels (optional)
- Use **SHAP or LIME** for interpretability
- Build a simple interface or dashboard for live predictions
- Expand model testing to external or real-world data

---

## 🧠 Conclusion

This project demonstrates that **behavioral and demographic data** can effectively predict mental health outcomes related to **mobile phone addiction**. The best models achieved:
- ✅ **90% accuracy for anxiety**
- ✅ **88% accuracy for depression**
- ✅ **80% accuracy for sleep quality issues**

showing potential for use in early screening and mental health monitoring applications.

---

## 📁 Folder Structure (Optional)


