# **Day 6 - Support Vector Machine (SVM) for Breast Cancer Classification**

## **Objective:**
In this project, we will build a **Support Vector Machine (SVM)** model to classify breast cancer data into two categories: malignant and benign tumors.

## **Dataset:**
We will use the **Breast Cancer Wisconsin (Diagnostic) dataset**. This dataset contains 30 features, including characteristics of the cell nuclei present in breast cancer biopsies. The goal is to classify tumors based on these features.

🎯 What is SVM?
Support Vector Machines are supervised machine learning algorithms used for classification (and sometimes regression). The goal of an SVM is to find a decision boundary (or hyperplane) that best separates the data into different classes.

Imagine you’re trying to classify emails as either spam or not spam based on various features like the content of the email. SVM will try to find the best boundary (line, plane, or higher-dimensional surface) that separates these two classes.
🧠 Key Concepts in SVM:
1. Hyperplane
A hyperplane is a decision boundary that separates the different classes. In 2D, this is just a straight line. In 3D, it's a plane. For higher-dimensional data, it’s a hyperplane.

The goal of SVM is to find the hyperplane that separates the data into two classes with the maximum margin.

2. Support Vectors
Support vectors are the data points that are closest to the hyperplane. These points are the most important because they define the margin. The position of the support vectors is what determines where the decision boundary (hyperplane) will be.

If you remove a support vector, the hyperplane may change. But if you remove other data points that are not support vectors, the hyperplane won't change.

3. Margin
The margin is the distance between the closest data points (support vectors) and the decision boundary. SVM works by maximizing the margin. The larger the margin, the better the generalization of the model to unseen data.

Think of it like trying to draw a line between two groups of points, and you want the line to be as far away as possible from the points on either side. The larger the margin, the better it should perform on new data.****
