# Spotify AI Recommender

## Overview
This project is an interactive Streamlit application that analyzes Spotify track data, evaluates machine learning models for mood prediction, and recommends songs based on a user’s audio profile.

It combines exploratory data analysis (EDA), model evaluation, and a content-based recommendation system into a single dashboard.

---

## Live Application
🔗 https://musicrecommendation-untmnqgwl6lkwamzndobfz.streamlit.app/

You can explore the application directly using the link above. Upload a playlist in JSON format or interact with the dashboard to analyze and generate recommendations.

---

## Problem Statement
With millions of songs available on streaming platforms, users often struggle to discover music that aligns with their preferences.

Most recommendation systems rely on popularity or collaborative filtering, which may not capture individual taste effectively.

This project addresses that by using audio features to:
- understand song characteristics  
- build a user preference profile  
- generate personalized recommendations  

---

## Features

### 1. Exploratory Data Analysis (EDA)
- Dataset summary statistics  
- Genre and language distribution visualizations  
- Feature correlation heatmap  
- Interactive histogram for selected features  

---

### 2. Model Evaluation
Performs binary classification of song mood using valence (`valence > 0.5`).

Models evaluated:
- K-Nearest Neighbors  
- Random Forest  
- Logistic Regression  
- Support Vector Machine (RBF)  
- XGBoost  
- Stacking Ensemble  

Evaluation metrics:
- Accuracy  
- F1-score  
- ROC AUC  
- Classification Report  

---

### 3. Song Recommendation System
- Upload a `.json` playlist of liked songs  
- System computes a user audio profile  
- Recommends similar songs using cosine similarity  

Filtering options:
- Genre-based filtering  
- Mood-based filtering:
  - Energetic & Happy  
  - Calm & Low-Valence  

Additional:
- PCA visualization of song clusters  

---

### 4. Feedback-Based Personalization
- Users can mark songs as **liked** or **disliked**  
- Feedback dynamically adjusts recommendations within the session  
- Improves relevance by refining the user preference profile  

---

## Dataset
- **Source:** Spotify Tracks Dataset (Kaggle)  
- **Size:** ~98,000 songs  

### Key Features:
- danceability  
- energy  
- valence  
- acousticness  
- instrumentalness  
- liveness  
- speechiness  
- tempo  
- loudness  

---

## Methodology

### Data Processing
- Removed duplicates and handled missing values  
- Scaled numerical features using StandardScaler  
- Aggregated user-liked songs to create a preference profile  

---

### Recommendation Logic
- Used cosine similarity to compare songs  
- Ranked songs based on similarity to the user profile  
- Returned top-N recommendations  

---

### Filtering
- Genre filtering using `track_genre`  
- Mood filtering based on valence and energy  

---

## Tech Stack
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Streamlit  
- XGBoost  
- Matplotlib  
- Seaborn  

---

## Project Structure
```
app/
data/
README.md
requirements.txt
```

---

## Installation

### 1. Download the project
Download the repository or clone it from GitHub.

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the application
```bash
streamlit run app/spotify_application.py
```

### 4. Open in browser
After running, the app will open automatically.  
If not, go to: http://localhost:8501  

---

## JSON Format for Input
The uploaded `.json` file should follow this structure:

```json
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
  }
]
```

---

## Key Insights
- Audio features effectively capture user music preferences  
- Content-based filtering avoids cold-start issues  
- Feedback (liked/disliked) improves recommendation relevance  
- Combining similarity + filtering enhances personalization  

---

## Results
The system provides personalized song recommendations by leveraging audio feature similarity and user feedback. It also enables model comparison for mood prediction, offering both analytical and practical insights in a single application.
