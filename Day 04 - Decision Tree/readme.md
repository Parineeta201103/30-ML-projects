# 📚 Day 04 – Student Result Predictor using Decision Tree

This project is part of the **30 Days, 30 ML Projects** challenge. On Day 4, we build a **Decision Tree Classifier** to predict whether a student will **Pass or Fail**, based on study habits, attendance, and other academic behaviors.

---

## 🧠 Project Objective

To use a **Decision Tree Classifier** to predict student performance using features like:
- Hours studied
- Attendance
- Previous academic score
- Assignment submission status
- Participation in extra classes

---

## 📁 Dataset

A synthetic dataset was generated with 30 student records and the following features:

| Feature                | Type     | Description                          |
|------------------------|----------|--------------------------------------|
| `Hours_Studied`        | Numeric  | Daily study hours                    |
| `Attendance`           | Numeric  | Class attendance percentage          |
| `Previous_Score`       | Numeric  | Score in the previous exam           |
| `Assignments_Submitted`| Categorical (Yes/No) | Whether assignments were submitted |
| `Extra_Classes`        | Categorical (Yes/No) | Participation in extra classes     |
| `Result`               | Target (Pass/Fail)   | Final outcome                       |

---

## 🧪 Techniques Used

- **Exploratory Data Analysis (EDA)** with `seaborn` and `matplotlib`
- **Preprocessing** using:
  - `OrdinalEncoder` for categorical features
  - `LabelEncoder` for target variable
- **Train-Test Split** (80-20)
- **Model Training** using `DecisionTreeClassifier (entropy)`
- **Evaluation** using:
  - Accuracy Score
  - Confusion Matrix
  - Classification Report
- **Tree Visualization** with `plot_tree()`

---

## 📊 Key Findings

- Students with:
  - More than **5 hours of study per day**
  - **High attendance**
  - Consistently submitted assignments  
  ...had a **much higher chance of passing**.
- **Hours_Studied**, **Assignments_Submitted**, and **Previous_Score** were the most influential features.

---

## 🌳 Model Performance

| Metric         | Score |
|----------------|-------|
| Accuracy       | ~ (insert your accuracy here) |
| Precision/Recall | Good on both Pass and Fail classes |
| Visualization  | Clear, interpretable tree structure |

---

## 📌 Conclusion

The Decision Tree successfully predicts student outcomes based on academic behavior. The model can be extended further with more data or compared with ensemble methods like Random Forest.

---

## 📁 Files

- `student_result_predictor.py` → Main code file
- `day04_findings.txt` → Summary of insights
- `README.md` → Project overview

---

## ✅ To Run

```bash
python student_result_predictor.py

