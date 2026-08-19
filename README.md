# 🎵 Hybrid Explainable Spotify Music Recommendation System

A hybrid music recommendation system that combines **Content-Based Filtering using KNN** and **Collaborative Filtering using SVD** to generate personalized music recommendations. An **Explainable AI (XAI)** module provides similarity scores, confidence scores, and feature-based explanations for each recommendation.

---

## 📌 Project Overview

Music streaming platforms provide access to millions of songs, making it difficult for users to discover music that matches their preferences.

This project addresses this problem by combining two recommendation approaches:

- **Content-Based Filtering** – recommends songs based on similar audio characteristics.
- **Collaborative Filtering** – predicts user preferences based on listening interactions.
- **Hybrid Recommendation** – combines both approaches to improve personalization.
- **Explainable AI** – provides understandable reasons behind each recommendation.

The system is developed using Spotify song metadata and audio features and is implemented in Python using machine learning techniques.

---

## 🎯 Objectives

- Generate personalized music recommendations.
- Identify songs with similar musical characteristics.
- Learn user preferences from listening interactions.
- Combine content-based and collaborative filtering.
- Provide transparent explanations for recommendations.
- Support discovery of both popular and lesser-known songs.

---

## 🛠️ Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **Surprise**
- **Matplotlib**
- **Seaborn**
- **Google Colab**
- **Machine Learning**
- **Explainable AI (XAI)**

---

## 📊 Dataset

The project uses a Spotify songs dataset containing approximately **114,000 tracks** with audio features and metadata.

### Key Features

| Feature | Description |
|---|---|
| Danceability | Measures how suitable a track is for dancing |
| Energy | Represents the intensity and activity of a track |
| Tempo | Speed of the track measured in BPM |
| Loudness | Overall loudness of the track |
| Acousticness | Probability that the track is acoustic |
| Speechiness | Presence of spoken words in the track |
| Instrumentalness | Likelihood that the track contains no vocals |
| Liveness | Detects the presence of a live audience |
| Valence | Represents the musical positivity or mood |
| Popularity | Popularity score of the track |
| Genre | Musical genre of the track |
| Artist | Artist performing the track |

---

## 🔍 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the dataset and identify useful patterns before model development.

### 1. Genre Distribution

The dataset contains a relatively balanced distribution of songs across genres, reducing genre bias and allowing the model to learn diverse musical patterns.

### 2. Correlation Analysis

The correlation heatmap revealed relationships between audio features such as **energy, loudness, and acousticness**. These relationships helped identify informative features for content-based recommendation.

### 3. Popularity Distribution

The dataset contains both popular and lesser-known songs, supporting diverse recommendations and helping the system promote music beyond highly popular tracks.

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

- Handling missing values.
- Selecting relevant audio features.
- Removing unnecessary attributes.
- Standardizing numerical features using `StandardScaler`.
- Preparing user-song interaction data for collaborative filtering.
- Removing duplicate or irrelevant records where required.

These steps ensure that the data is suitable for both content-based and collaborative filtering models.

---

## 🤖 Recommendation Methodology

The proposed system consists of three major recommendation components.

### 1. Content-Based Filtering — KNN

The **K-Nearest Neighbors (KNN)** algorithm with **cosine distance** is used to identify songs with similar audio characteristics.

The following features are used:

- Danceability
- Energy
- Key
- Loudness
- Mode
- Speechiness
- Acousticness
- Instrumentalness
- Liveness
- Valence
- Tempo
- Popularity

The features are standardized before applying KNN to ensure that differences in feature scales do not affect similarity calculations.

---

### 2. Collaborative Filtering — SVD

**Singular Value Decomposition (SVD)** is used to learn user preferences from user-song interaction data.

The model predicts how much a user may like an unseen song and assigns a predicted rating.

Example:

```text
User: User_1
Song: Believer
Predicted Rating: 4.06
```

### 3. Hybrid Recommendation

The hybrid recommendation system combines the outputs of Content-Based Filtering and Collaborative Filtering to generate personalized recommendations.

Content-Based Filtering + Collaborative Filtering → Hybrid Recommendation

This approach considers both the similarity between songs and the user's predicted preferences.

---

## 💡 Explainable AI (XAI)

The Explainable AI module provides understandable reasons behind each recommendation.

It generates:

- Similarity Score
- Confidence Score
- Genre Match
- Energy Similarity
- Danceability Similarity
- Tempo Similarity
- Popularity Similarity

Example:

```text
Track: Ghost Town
Predicted Rating: 4.08
Similarity: 88.4%
Confidence: 77.2%

Explanation:
Genre Match: No
Energy Match: 94.1%
Danceability Match: Similar
Popularity Match: Similar
```

###System Workflow
Spotify Dataset
      ↓
Data Preprocessing
      ↓
Exploratory Data Analysis
      ↓
 ┌───────────────┐
 │               │
 ↓               ↓
KNN             SVD
Content-Based   Collaborative
Filtering       Filtering
 │               │
 └───────┬───────┘
         ↓
Hybrid Recommendation
         ↓
Explainable AI
         ↓
Personalized Recommendations
