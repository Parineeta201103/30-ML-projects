# Day 7: Naive Bayes - Email Spam Detection

## 🚀 Goal
Build a Naive Bayes classifier to detect whether a message is spam or not.

🌟 What is Naive Bayes?
Naive Bayes is a probabilistic machine learning algorithm based on Bayes’ Theorem with a strong (naive) assumption:

All features are independent given the class.

Even though this assumption is often not true in real life, it still works surprisingly well in many applications!

⚙️ How Naive Bayes works:
Calculate prior for each class.

Compute likelihood of features for each class.

Multiply them to get the posterior (we skip evidence for comparison).

Pick the class with the highest posterior probability.

🍭 Types of Naive Bayes:
Gaussian Naive Bayes – Assumes features follow a normal distribution (used for continuous data).

Multinomial Naive Bayes – Works well with text data, counts word frequencies.

Bernoulli Naive Bayes – Binary features (e.g., word appears or not).

📦 Applications:
Spam detection

Sentiment analysis

Document classification

Disease prediction

🚀 Pros:
Fast and simple

Works well with high-dimensional data (like text!)

Performs surprisingly well even with unrealistic independence assumption

⚠️ Cons:
Assumes features are independent

Struggles when features are correlated or dependent

## 📊 Dataset
- **Dataset:** SMS Spam Collection
- **Source:** [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection)
- Each entry is labeled as `spam` or `ham`, along with the message text.
- web page:](http://www.dt.fee.unicamp.br/~tiago/smsspamcollection)

## 🔧 Techniques Used
- Text preprocessing (lowercasing, removing punctuation, stopwords)
- TF-IDF Vectorization
- Naive Bayes Classifier (MultinomialNB)
- Model evaluation using accuracy, confusion matrix, and classification report

## 📈 Results
Achieved good performance using a simple and efficient Naive Bayes model on preprocessed text data.

## 📁 Files
- `spam_classifier_nb.ipynb`: Full notebook with EDA, preprocessing, model building
- `spam.csv`: Dataset (if license allows)
- `requirements.txt`: All required Python packages

