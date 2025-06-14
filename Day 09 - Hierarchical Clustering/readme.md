# 📊 Day 09 - Hierarchical Clustering: Country Clustering

### 🔍 Project Overview
This project applies **Hierarchical Clustering** (Agglomerative approach) to group countries based on multiple **socioeconomic indicators** such as income, health, inflation, GDP, and more. The objective is to discover hidden patterns among countries and form **clusters with similar development profiles**.

---

### 🎯 Motivation
In a globally diverse world, countries show major variations in economic and social indicators. Policymakers and international organizations often need to classify countries into similar groups to:
- Distribute aid and healthcare resources efficiently.
- Develop regional policies for clusters of nations.
- Analyze development progress and challenges.
  
“The motivation is to find natural groupings of countries based on multi-dimensional socioeconomic features. It helps governments and international agencies make informed, data-driven decisions regarding funding, policy-making, and global partnerships. Hierarchical clustering is particularly useful here because it allows us to visualize how countries are related without pre-defining the number of groups, which is perfect for exploratory socio-economic analysis.”
Hierarchical clustering helps reveal **natural groupings** without prior knowledge of the number of clusters and provides interpretable visualizations like **dendrograms**.

---

### 🧠 What is Hierarchical Clustering?
Hierarchical Clustering builds a **tree of clusters**:
- We use the **Agglomerative** approach (bottom-up).
- Starts with each country as its own cluster, and successively merges the closest pairs.
- A **dendrogram** is used to visualize the process and decide the number of clusters.

---

### 📁 Dataset
- Source: [Country-data.csv](https://www.kaggle.com/datasets/rohan0301/unsupervised-learning-on-country-data)
- Features include: Income, Health, Life Expectancy, Exports, Inflation, Fertility, etc.
- Target: No explicit labels – this is an **unsupervised learning** problem.

---

### 🔧 Steps Followed
1. Loaded and cleaned the dataset.
2. Scaled the features using `StandardScaler`.
3. Built a dendrogram using `scipy.cluster.hierarchy`.
4. Chose number of clusters and labeled countries.
5. Visualized clusters using PCA for 2D projection.
6. Analyzed and interpreted clusters.

---

### 📊 Results & Analysis
- Countries were grouped into meaningful clusters.
- Cluster examples:
  - Cluster 1: High GDP, low fertility – Developed countries
  - Cluster 2: High fertility, low income – Developing nations
- Dendrogram helped visually choose 4 optimal clusters.
- Silhouette Score used to evaluate cluster quality.

---

### 📈 Visualizations
- Dendrogram to identify clusters.
- PCA-based scatter plot to visualize cluster separations.

---

### 📦 Libraries Used
- `pandas`, `numpy`
- `scikit-learn`
- `matplotlib`, `seaborn`
- `scipy` (for hierarchical clustering)

---

### ✅ Key Learnings
- How to use **Agglomerative Clustering** in real-life datasets.
- How to interpret a **dendrogram** and form clusters from it.
- Application of clustering in **policy-making and global analysis**.

