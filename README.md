# Recommendation Systems - Complete Projects Overview

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-1.5.3-lightgrey?logo=pandas&logoColor=black)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.2.2-orange?logo=scikit-learn&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12.2-blue?logo=seaborn&logoColor=white)

This repository contains multiple **recommendation system projects** implemented in Python using datasets from Kaggle and GroupLens.

---

## Table of Contents

1. [Collaborative Filtering using k-Nearest Neighbors (kNN)](#1-collaborative-filtering-using-k-nearest-neighbors-knn)
2. [Pearson Correlation-Based Recommendations](#2-pearson-correlation-based-recommendations)
3. [MovieLens Collaborative Filtering](#3-movielens-collaborative-filtering)
4. [Content-Based Recommendation System](#4-content-based-recommendation-system)
5. [Average Weighted Recommendation Engine](#5-average-weighted-recommendation-engine)
6. [Overall Summary](#overall-summary)

---

## 1. Collaborative Filtering using k-Nearest Neighbors (kNN)

- **Dataset:** Book-Crossing dataset (`BX-Books.csv`, `BX-Users.csv`, `BX-Book-Ratings.csv`)  
- **Objective:** Recommend books to users based on similarity between users or items.  
- **Approach:**
  - Cleaned datasets and filtered popular books (minimum rating count threshold).  
  - Focused on users from the US and Canada.  
  - Converted ratings table to a 2D matrix and filled missing values with zeros.  
  - Used `scipy` sparse matrices for efficiency.  
  - Applied **kNN algorithm** with cosine similarity to find nearest neighbors.  
- **Result:** Able to recommend similar books based on user ratings.

---

## 2. Pearson Correlation-Based Recommendations

- **Dataset:** Book-Crossing dataset  
- **Objective:** Recommend books by calculating correlation between book ratings.  
- **Approach:**
  - Computed average ratings and total rating counts for each book.  
  - Excluded users with <200 ratings and books with <100 ratings.  
  - Created a user-item pivot table.  
  - Used **Pearson correlation coefficient** to find similar books.  
- **Result:** Provided recommendations based on linear correlations.

---

## 3. MovieLens Collaborative Filtering

- **Dataset:** MovieLens (`movies.csv`, `ratings.csv`)  
- **Objective:** Recommend movies based on user ratings using kNN.  
- **Approach:**
  - Merged movie and ratings datasets.  
  - Filtered movies with ≥50 ratings.  
  - Built a user-movie pivot table.  
  - Applied **kNN with cosine similarity**.  
- **Result:** Recommended movies liked by similar users.

---

## 4. Content-Based Recommendation System

- **Dataset:** TMDB movie metadata (`tmdb_5000_movies.csv`, `tmdb_5000_credits.csv`)  
- **Objective:** Recommend movies based on plot summaries.  
- **Approach:**
  - Merged credits and movies datasets; cleaned irrelevant columns.  
  - Filled missing overviews.  
  - Applied **TF-IDF vectorization** on movie overviews.  
  - Computed **sigmoid kernel** to measure similarity.  
  - Created a reverse mapping of indices to titles.  
  - Built a function to recommend top 10 similar movies.  
- **Result:** Recommended movies with similar storylines.

---

## 5. Average Weighted Recommendation Engine

- **Dataset:** TMDB movies dataset  
- **Objective:** Combine movie ratings and popularity for ranking.  
- **Approach:**
  - Calculated **weighted average**:  
    \[
    \text{Weighted Average} = \frac{(R \times v) + (C \times m)}{v + m}
    \]  
  - Scaled `weighted_average` and `popularity` using `MinMaxScaler`.  
  - Computed final score as 50% weighted average + 50% popularity.  
  - Visualized top movies by score.  
- **Result:** Recommended movies that are **highly rated** and **popular**.

---

## Overall Summary

These projects cover **collaborative filtering (user/item-based), content-based filtering, Pearson correlation, kNN, and weighted average recommendation systems**.  
They demonstrate how to generate tailored recommendations based on ratings, similarity, and content features, providing a **comprehensive understanding of modern recommendation engines**.


