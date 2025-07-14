# 📊 Day 10 - PCA: Wine Dataset Visualization

## ✅ Objective
To reduce the dimensionality of the Wine dataset using PCA and visualize the class separation between different types of wines.

## 📁 Dataset
**Wine Dataset** from scikit-learn – contains 13 chemical features for 3 classes of wine.

## 🔧 Techniques Used
- StandardScaler (for normalization)
- Principal Component Analysis (PCA)
- 2D Scatter Plot with Seaborn
- Explained Variance Plot

## 📉 Insights
- PC1 and PC2 capture ~55% of total variance
- Clear class separation observed in PCA plot → PCA is effective here
- Dimensionality reduced from 13 to 2 with just loss of half of information
- If we need 95% variance to be explained we need 8 components.

## 💡 Why PCA?
- Helps in visualizing complex high-dimensional data
- Reduces computational cost and risk of overfitting
- Great for EDA and preprocessing before model building.
