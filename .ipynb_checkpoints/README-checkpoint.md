# Trends & Explicitness in Spotify Songs (EDA + Modeling)

## Why this project?
I wanted a data-driven way to talk music with my daughters, who live on Spotify. Using a public dataset of ~237k Spotify tracks, I explored how musical features change over time and whether we can predict if a track is explicit from audio features. 

## Live project page: https://musicproject1.carrd.co/ 
## Repo: https://github.com/markcoty/light-spotify-dataset

## Highlights

- **Dataset:** ~237,000 Spotify tracks (1900s–2024) with 18 features (artist, song, year, energy, danceability, etc.). 
- **Exploratory findings:**
  - Energy and Loudness are strongly positively correlated.
  - Danceability vs. Tempo shows a clear curved (nonlinear) pattern centered around ~120 BPM.
  - Explicit tracks become more common in the late 1990s onward.
- **Modeling:** Predicting “explicit” using classical ML (Logistic Regression, Decision Tree, Random Forest). 
  - Top model (Random Forest) reached ~0.86 accuracy on a stratified holdout set.
- **Statistical tests:** Two-sample tests support relationships between Energy/Danceability and Popularity; and pre-2008 vs. post-2008 explicitness.

🎯 **What I learned:** Cleaning/EDA on a large music dataset; careful handling of imbalanced labels; building simple, reproducible ML baselines; packaging results for a portfolio.

**Repo Structure**

- ├─ Notebook/
- │ └─ light-spotify-dataset-v2.ipynb (EDA → models → tests)
- ├─ Images/ 
- ├─ Data/ 
- ├─ requirements.txt
- └─ README.md

## Quickstart ##

**Environment**
[bash]
python -m venv .venv && source .venv/bin/activate   # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt

**Data:**
Download the CSV from Kaggle (see Data folder or project page) and place it at Data/spotify.csv.

**Run:**
Open and run Notebook/light-spotify-dataset-v2.ipynb top-to-bottom.

**Reproducibility:**
Fixed random seed for all splits and models.

Stratified train/test split on the Explicit label.

All charts are saved from the notebook into Images/ on execution.

**Methods:** (brief)
EDA: bar charts for categorical fields; histograms + correlations for numeric fields; selected bivariate plots (e.g., Energy vs. Loudness, Danceability vs. Tempo).

**Modeling:** Logistic Regression, Decision Tree, Random Forest using a simple sklearn Pipeline; evaluation with accuracy, precision, recall, F1, ROC-AUC; confusion matrix.

**Statistical tests:** z-test / two-sample t-tests for relationships of interest.

**Results:** (short)
Nonlinear relationships: Danceability peaks around ~120 BPM.

**Trend:** Explicit tracks grow in prevalence in the late 1990s onward.

**Modeling:** Random Forest ~0.86 accuracy predicting “explicit” using features such as Loudness, Energy, Speechiness, and Tempo; baselines reported for transparency.

**Limitations:**
- Genre labeling in public datasets can be noisy and inconsistent.
- Popularity depends on platform/time—interpret with caution.
- Models are baseline, not production systems.

**What’s Next:**
- AWS pipeline (separate project): ingest Spotify API data to S3 → Glue Catalog → Athena → QuickSight for live analysis.
- Extend features (e.g., time windows, artist-level aggregates).
- Try regularized logistic regression and calibrated probabilities.

**Author:**
L. Mark Coty – data engineer, mathematician, and history enthusiast exploring data through music.



For a fuller rendering of this ReadMe, along with a few details not shown here, visit this link:
### [Project Website](https://musicproject1.carrd.co/ "Spotify Dataset Project")
