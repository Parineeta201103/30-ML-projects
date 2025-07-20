# 🎬 Movie Recommender System using Collaborative Filtering

## 📝 Overview

This project implements a **movie recommendation system** using **Collaborative Filtering** on a user-item rating matrix. Given a user ID, the system recommends movies based on the preferences of other users who have similar tastes. The goal is to simulate a real-world recommender engine like the ones used by Netflix, Amazon Prime, or IMDB.

---

## 🤝 What is Collaborative Filtering?

**Collaborative Filtering** is a recommendation approach based on the idea that users who agreed in the past will agree in the future about item preferences.

There are two types:
1. **User-Based Collaborative Filtering**: Recommend items to a user based on what similar users liked.
2. **Item-Based Collaborative Filtering**: Recommend items similar to what the user liked in the past.

**In this project, we use User-Based Collaborative Filtering**. The similarity between users is measured using **cosine similarity**, and recommendations are made based on top similar users.

---

## 📁 Dataset

We use the [MovieLens dataset]:
- `movies.csv`: Movie IDs, Titles, Genres
- `ratings.csv`: User IDs, Movie IDs, Ratings, Timestamps

---

## 🧪 Project Workflow

### 🔹 Step 1: Load Libraries and Dataset

```python
import pandas as pd
ratings = pd.read_csv("ratings.csv")
movies = pd.read_csv("movies.csv")
```

- `ratings.csv` contains user-movie interactions
- `movies.csv` contains movie metadata

---

### 🔹 Step 2: Create User-Item Matrix

```python
user_item_matrix = ratings.pivot(index='userId', columns='movieId', values='rating')
user_item_matrix.fillna(0, inplace=True)
```

- This matrix contains users as rows and movies as columns, with cell values as ratings
- Missing values are filled with 0, indicating no interaction

---

### 🔹 Step 3: Compute User Similarity

```python
from sklearn.metrics.pairwise import cosine_similarity
user_sim_matrix = cosine_similarity(user_item_matrix)
user_sim_df = pd.DataFrame(user_sim_matrix, index=user_item_matrix.index, columns=user_item_matrix.index)
```

- `cosine_similarity` computes similarity between users based on their rating vectors
- The result is a square matrix with similarity scores between all users

---

### 🔹 Step 4: Generate Recommendations

```python
def get_user_recommendations(user_id, num_recommendations=5):
    sim_scores = user_sim_df[user_id].drop(user_id)
    top_users = sim_scores.sort_values(ascending=False).head(5).index
    similar_user_ratings = user_item_matrix.loc[top_users]
    mean_ratings = similar_user_ratings.mean(axis=0)
    movies_watched = user_item_matrix[user_id].dropna().index
    unseen_movies = mean_ratings.drop(movies_watched, errors='ignore')
    movie_id_to_title = dict(zip(movies['movieId'], movies['title']))
    unseen_movies.index = unseen_movies.index.map(movie_id_to_title)
    return unseen_movies.sort_values(ascending=False).head(num_recommendations)
```

- This function finds top 5 similar users to the input `user_id`
- It averages their movie ratings and recommends top N movies not yet watched by the user
- Movie IDs are mapped back to titles for interpretability

---

### 🔹 Step 5: Example Output

```python
get_user_recommendations(user_id=300, num_recommendations=5)
```

**Output:**
```
Harry Potter and the Sorcerer's Stone (2001)     5.0  
The Hunger Games: Mockingjay - Part 1 (2014)     5.0  
Ponyo (2008)                                     5.0  
The Good, the Bad and the Ugly (1966)            5.0  
Divergent (2014)                                 5.0  
```

---

## 📌 Key Insights

- The model recommends unseen movies based on opinions of similar users
- Highly rated and popular movies naturally rank higher if liked by similar users
- Cosine similarity works well on sparse rating matrices like MovieLens

---

## 🛠️ Technologies Used

- Python
- pandas, NumPy
- scikit-learn (`cosine_similarity`)
- MovieLens Dataset

---

## 💡 Future Improvements

- Apply Item-Based Collaborative Filtering
- Use Matrix Factorization (e.g., SVD)
- Implement Hybrid Recommendations (Content + Collaborative)
- Add timestamp weighting for recent interactions

---

