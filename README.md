# Spotify AI Recommender

This is an interactive Streamlit web app that analyzes Spotify track data, evaluates ML models for music mood prediction, and recommends songs based on a user’s audio profile. The system uses content-based filtering via cosine similarity and offers EDA tools, classification reports, and PCA visualizations — all in one dashboard.

Streamlit App: https://musicrecommendation-untmnqgwl6lkwamzndobfz.streamlit.app/


## Features

### 1. EDA Dashboard
- View dataset summary statistics
- Bar charts of genre and language distributions
- Heatmap of feature correlations
- Select any feature to plot its histogram

### 🤖 2. Model Evaluation
- Binary classification of song mood based on valence (> 0.5)
- Trains and compares models:
  - K-Nearest Neighbors
  - Random Forest
  - Logistic Regression
  - Support Vector Machine (RBF)
  - XGBoost
  - Stacking Ensemble
- Reports: Accuracy, F1-score, ROC AUC, Classification Report

### 3. Song Recommendation System
- Upload a `.json` playlist (liked songs) with Spotify audio features
- App computes user’s average audio profile
- Recommends similar songs using cosine similarity
- Filter recommendations:
  - By Genre
  - By Mood (Energetic & Happy, or Calm & Low-Valence)
- Optional PCA visualization of song clusters



### Prerequisites
Python 3.7 or higher

### Installation

1. Clone the repository:
git clone https://github.com/yourusername/spotify-ai-recommender.git
cd spotify-ai-recommender

2. Install required packages:
pip install -r requirements.txt

3. Run the app:
streamlit run spotifyapp.py
Ensure spotify_tracks.csv is in the same folder.

JSON Format for Upload
Your uploaded .json should look like this:

[
  {
    "track_name": "Song A",
    "danceability": 0.75,
    "energy": 0.82,
    "loudness": -5.0,
    "speechiness": 0.05,
    "acousticness": 0.1,
    "instrumentalness": 0.0,
    "liveness": 0.1,
    "tempo": 120.0,
    "duration_ms": 210000
  },
  {
    "track_name": "Song B",
    "danceability": 0.65,
    ...
  }
]
