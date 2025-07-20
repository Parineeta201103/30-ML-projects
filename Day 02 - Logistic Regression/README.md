# 🌸 Day 02 - Logistic Regression: Iris Flower Classification

## 📌 Project Overview

The goal of this project is to classify iris flowers into three species — **Setosa**, **Versicolor**, and **Virginica** — based on their physical measurements. The algorithm used is **Logistic Regression**, a fundamental classification technique in machine learning.

This exercise builds intuition for **multiclass classification**, model evaluation, and feature impact analysis on categorical predictions.

---

## 📊 Dataset Description

The project uses the classic **Iris dataset**, widely used for benchmarking classification models.

### 🔹 Dataset Characteristics:
- **Total Samples**: 150
- **Number of Classes**: 3
  - *Setosa*
  - *Versicolor*
  - *Virginica*
- **Features Used**:
  - Sepal Length (cm)
  - Sepal Width (cm)
  - Petal Length (cm)
  - Petal Width (cm)

This dataset is small, balanced, and clean, making it ideal for exploring simple yet powerful classification algorithms like Logistic Regression.

---

## 🤖 Algorithm: Logistic Regression

**Logistic Regression** is a linear model used for **binary** and **multiclass classification** problems. It models the probability that a given input belongs to a certain class using the **logit (sigmoid) function**.

### Why Logistic Regression?

- Interpretable and fast
- Performs well on linearly separable data
- Provides probability estimates
- Easily extendable to multiclass tasks using a **one-vs-rest (OvR)** or **softmax (multinomial)** approach

In this project, Logistic Regression is used in its **multinomial** form to classify among three classes.

---

## 🧪 Model Evaluation

To assess model performance, several key metrics were used:

- **Accuracy**: Proportion of correctly classified instances.
- **Precision**: Proportion of true positives out of all predicted positives.
- **Recall**: Proportion of true positives out of all actual positives.
- **F1-score**: Harmonic mean of precision and recall — balances the two.
- **Confusion Matrix**: Visual representation of correct vs incorrect classifications across each class.

These metrics provide a well-rounded evaluation, especially in multiclass settings.

---

## 📈 Visualization

To better interpret the model's performance:

- A **confusion matrix** is plotted to observe the number of correct and incorrect predictions for each class.
- The matrix helps identify which flower species are being confused with one another.

---

## 🧠 Key Learnings

- Logistic Regression can effectively handle **multiclass classification** using a probabilistic approach.
- **Feature importance** can be interpreted through model coefficients, giving insights into how each input affects prediction.
- Evaluation through metrics like **F1-score** and **confusion matrix** is essential for understanding real-world model performance, beyond just accuracy.
