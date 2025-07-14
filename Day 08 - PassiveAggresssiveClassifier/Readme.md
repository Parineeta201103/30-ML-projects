# 📰 Fake News Detection Using PassiveAggressiveClassifier

This project aims to classify news articles as **real** or **fake** using Natural Language Processing (NLP) techniques and the **PassiveAggressiveClassifier** from scikit-learn. It was completed as part of a machine learning project and uses a labeled dataset from Kaggle.

---

## 📁 Dataset

The dataset was sourced from Kaggle: 

It includes:
- `Fake.csv` – contains fake news articles
- `True.csv` – contains real news articles

Each article has the following fields:
- `title`
- `text`
- `subject`
- `date`

---

## 🧠 Model Used

**PassiveAggressiveClassifier**  
A fast and efficient online learning algorithm ideal for large-scale text classification. It remains passive when the prediction is correct and becomes aggressive in case of a misclassification.

---

## 🔧 Libraries & Tools

- Python
- Pandas & NumPy
- Scikit-learn
- TfidfVectorizer
- Matplotlib & Seaborn

---

## 🧪 Project Workflow

1. **Data Loading**  
   Load and label the datasets (`1` for real, `0` for fake).

2. **Merging & Preprocessing**  
   Concatenate datasets and clean/prepare the text data.

3. **TF-IDF Vectorization**  
   Transform textual data into numerical features using `TfidfVectorizer` with stopword removal and `max_df=0.7`.

4. **Train-Test Split**  
   Split the dataset into training and validation sets (80-20).

5. **Model Training**  
   Train a PassiveAggressiveClassifier with `max_iter=50`.

6. **Model Evaluation**  
   - Accuracy Score: `~99.5%`
   - Precision, Recall, F1-Score: Very high across both classes
   - Confusion matrix visualization

---

## 📊 Results

- ✅ **Accuracy**: 99.5%
- 🔍 **Classification Report**:
  - Precision, Recall, F1-score all ~1.00 for both classes
- 🧾 **Confusion Matrix** shows minimal misclassifications

---

## 📌 Key Takeaways

- TF-IDF effectively highlights important terms for classification.
- PassiveAggressiveClassifier is lightweight and high-performing for text data.
- Even with minimal feature engineering, high accuracy was achieved.

---

## 🚀 Future Scope

- Use deep learning models like LSTM or BERT for comparison.
- Add more metadata features such as publisher credibility or user engagement.
- Deploy the model as a web app using Streamlit or Flask.

---


