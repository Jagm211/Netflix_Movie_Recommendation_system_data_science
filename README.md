# 🎬 Netflix Movie Recommendation System

A hybrid movie recommendation engine built using Content-Based Filtering and Collaborative Filtering techniques on the MovieLens dataset.

## 🚀 Live Demo
> Google Colab Notebook — [Open in Colab](#)

---

## 📌 Overview

This project replicates the core recommendation logic used by platforms like Netflix. It combines two powerful techniques:
- *Content-Based Filtering* — recommends movies similar in genre using TF-IDF + Cosine Similarity
- *Collaborative Filtering* — recommends movies based on user behavior using SVD Matrix Factorization
- *Hybrid System* — combines both approaches for better accuracy

---

## 📊 Dataset

- *Source:* [MovieLens Small Dataset](https://grouplens.org/datasets/movielens/latest/)
- *Movies:* 9,742
- *Ratings:* 100,836
- *Users:* 610

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core Language |
| Pandas & NumPy | Data Processing |
| Scikit-learn | TF-IDF, Cosine Similarity |
| SciPy (SVDs) | Matrix Factorization |
| Matplotlib & Seaborn | EDA & Visualizations |
| Google Colab | Development Environment |

---

## 🧠 Approach

### 1. Content-Based Filtering
- Extracted genre features from movie metadata
- Applied TF-IDF Vectorization on genres
- Computed Cosine Similarity between all movies
- Returns top-N similar movies for any given title

### 2. Collaborative Filtering (SVD)
- Built User-Movie rating matrix (610 × 9724)
- Applied mean normalization
- Used Singular Value Decomposition (k=50 latent factors)
- Reconstructed predicted ratings matrix

### 3. Hybrid System
- Weighted combination of Content (50%) + Collaborative (50%) scores
- Filters out already-watched movies
- Returns personalized ranked recommendations

---

## 📈 Model Performance

| Metric | Score |
|--------|-------|
| RMSE (Collaborative) | ~0.89 |
| Approach | Hybrid (Content + SVD) |

---

## 💻 Usage

```python
# Content-Based
content_based_recommend('Toy Story (1995)', n=10)

# Collaborative
collaborative_recommend(user_id=1, n=10)

# Hybrid
hybrid_recommend(user_id=1, title='Toy Story (1995)', n=10)
Author- Jagmeet Singh Nijhawan(Data Scientist)
