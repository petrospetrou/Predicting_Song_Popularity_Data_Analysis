# Modeling Song Popularity: Audio Features & Streaming Metadata Analysis

---

## Abstract

In the modern music industry, streaming platforms are central to determining a song’s success. This project analyzes how characteristics such as danceability, energy, and listener statistics impact popularity. Using a dataset of over 92,000 tracks enriched with Last.fm streaming metadata, I built predictive models to forecast song popularity and compare performance across classification and regression techniques.

---

## Objectives

- Understand and clean the dataset
- Engineer features and conduct exploratory data analysis (EDA)
- Train Random Forest Classifier and Regressor models
- Apply feature selection using RFI, VIF, and LASSO methods
- Evaluate model performance based on classification and regression metrics

---

## Dataset

The dataset was originally sourced from Kaggle:
https://www.kaggle.com/datasets/priyamchoksi/spotify-dataset-114k-songs/data

Additional fields `playcount` and `listeners` were fetched via the Last.fm API to enhance model training and prediction accuracy.

### Feature Highlights

| Feature           | Description                                      |
|------------------|--------------------------------------------------|
| danceability      | How suitable a track is for dancing (0–1)       |
| energy            | Intensity and activity of a track               |
| valence           | Positivity of the music                         |
| playcount         | Number of plays (from Last.fm)                  |
| listeners         | Unique listeners (from Last.fm)                 |
| song_popularity   | Target label (0–100 scale by Spotify)           |
| track_genre       | Song genre (categorical, one-hot encoded)       |

---

## Environment Setup

To run this project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ecs784-song-popularity-prediction.git
   cd ecs784-song-popularity-prediction
   ```

2. Set up a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Launch the Jupyter notebook:
   ```bash
   jupyter notebook ecs784_coursework1_code.ipynb
   ```

---

## Models Used

- **Random Forest Classifier**  
  Binary classification: Predicts whether a song is "popular" or "not popular".

- **Random Forest Regressor**  
  Regression model: Predicts the exact popularity score (0–100).

---

## Feature Selection Techniques

- **Random Forest Importance (RFI)**: Identifies features based on model-based importance.
- **Variance Inflation Factor (VIF)**: Removes features with high multicollinearity.
- **LASSO Regularization**: Shrinks less important feature coefficients to zero.

The best results were achieved by combining selected features from all three methods.

---

## Evaluation Metrics

### Classification (Random Forest Classifier):
- Accuracy: 0.8991
- Precision: 0.8805
- Recall: 0.8506
- F1-Score: 0.8639
- ROC AUC: 0.95

### Regression (Random Forest Regressor):
- Mean Squared Error (MSE): 178.45
- Mean Absolute Error (MAE): 8.70
- R-Squared (R²): 0.6523

---

## Repository Structure

```
.
├── ecs784_coursework1_code.ipynb         # Main notebook with full pipeline
├── ECS784_Coursework_1_Report.pdf        # Final academic report
├── ECS784_Coursework_1_Jupyter.pdf       # PDF export of annotated notebook
└── README.md                             # Project overview (this file)
```

---

## License

**Custom Academic License**

This project was created as part of a Master's degree in Computer Science at the University of Essex. It is subject to academic integrity policies and must not be reused or modified for commercial purposes without explicit permission from the author. For research and educational use only.

---

## Notes

This project was completed for ECS784 - Data Analytics coursework. It is intended for academic and learning purposes, and while methodologically sound, it is not optimized for production deployment.
