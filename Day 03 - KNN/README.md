# 🔢 Day 03 - KNN: Digit Classification with scikit-learn

In this project, I used the **K-Nearest Neighbors (KNN)** algorithm to classify handwritten digits from images using scikit-learn's `load_digits()` dataset.

---

## 🧠 Dataset Overview

- **Source**: `sklearn.datasets.load_digits()`
- **Samples**: 1797 images
- **Image Size**: 8 × 8 pixels
- **Classes**: 10 digits (0 through 9)

---

## 🤖 Model Info

- **Algorithm**: K-Nearest Neighbors (KNN)
- **Library**: scikit-learn
- **Main Parameters**:
  - `n_neighbors=3`

---

## ⚙️ Workflow

1. Loaded and visualized digit images
2. Flattened the image data (8×8 → 64 features)
3. Split into training and testing sets
4. Trained KNN classifier
5. Evaluated predictions with:
   - Accuracy
   - Confusion Matrix
   - Classification Report

---

## 🧩 How KNN Works (Simplified)

K-Nearest Neighbors (KNN) is a simple but powerful algorithm based on the idea of **"similar things stay close."** Here's how it classifies a new image:

1. **Measure Distance**  
   - For a new digit image, KNN compares it to all training images using **Euclidean distance**.
   - Each image is treated as a 64-dimensional vector (flattened from 8x8).

2. **Find Nearest Neighbors**  
   - It finds the **k closest training images** (we used `k = 3`).

3. **Vote**  
   - The labels of those neighbors are collected, and the **most common label wins**.
   - For example: if the nearest neighbors have labels `[3, 3, 5]`, the prediction is `3`.

4. **Predict**  
   - The model assigns the majority label to the test image.

💡 **Why KNN works here**: Handwritten digits with similar shapes tend to have similar pixel values — so they're close in feature space.

---

---

## 📈 Visualizations

- Confusion matrix using `seaborn.heatmap()`
- Sample digits with predicted labels

---

## 💡 Learnings

- Understood how KNN uses distance to classify instances
- Learned about performance trade-offs with different `k` values the greater the value of 'k' higher the bias , and the lesser the value of 'k' less the bias so we have to find a perfect value of k so that our model do not overfit or underfit.
- Explored evaluation of multiclass classification models

---
### 🔜 Up Next

➡️ Day 4: Decision Tree Classifier!




