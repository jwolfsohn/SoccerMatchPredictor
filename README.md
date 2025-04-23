# Match Predictor

This project uses historical Premier League data scraped from [fbref.com](https://fbref.com/en/comps/9/Premier-League-Stats) and applies machine learning models to predict the outcome of upcoming matches. Built in a Python Jupyter Notebook (Google Colab), it utilizes tools like BeautifulSoup, Pandas, and Scikit-learn.

---

## Overview

1. **Data Collection**
   - Scrapes team URLs and fixture tables from fbref.com
   - Uses `requests` and `BeautifulSoup` to extract links and table data from HTML `<a>` tags
   - Gathers match stats and shooting stats for each team
   - Cleans and merges data using `pandas`
   - Iterates across multiple seasons (2022, 2021) with rate-limiting to avoid IP bans

2. **Machine Learning**
   - Uses a `RandomForestClassifier` from `scikit-learn`
   - Predicts match outcomes based on:
     - Venue
     - Opponent
     - Match hour and day
     - Rolling averages over the last 3 matches (shots, goals, penalties, etc.)
   - Achieves ~67% prediction accuracy
   - Plans for improvements: include team rating weightings or explore neural networks

3. **Future Match Predictions**
   - Predicts the outcome of future matches (e.g., April 28, 2022) using only stats prior to April 25
   - Ensures no data leakage from future match results

---

## Setup

1. Open in Google Colab or any Jupyter environment.
2. Install required packages:
   ```bash
   pip install pandas scikit-learn beautifulsoup4 requests
