# Weather & Mood

**By María Martínez & Velia Alaminos**

---

## 🧠 Project Overview

This project investigates the potential relationship between weather conditions and the general mood of the population. We focused our analysis on **Barcelona (Spain)** and **Stockholm (Sweden)**, using daily weather data and sentiment scores derived from Twitter.

---

## 🎯 Objectives

- Explore whether variables like temperature, precipitation, and cloud cover impact daily mood in different regions.
- Use sentiment analysis from social media as a proxy for collective emotional states, measured on a 0–1 scale:
  - `0` → Very negative mood
  - `1` → Very positive mood

---

## 🔍 Methodology

### 1. Initial Exploration – Web Scraping & Public Sources

We began by exploring multiple ways to collect real-world sentiment data. Our initial plan included web scraping and extracting data from various public sources:

- **Reddit**: Attempted to scrape posts, but access was blocked due to restrictions in [Reddit’s robots.txt](https://www.reddit.com/robots.txt) and their [Public Content Policy](https://support.reddithelp.com/hc/en-us/articles/26410290525844-Public-Content-Policy).
- Then, we tried using **Reddit RSS feeds**, but they were limited and didn’t match our scope.
- We gathered data from other RSS feeds and websites:
  - **BBC News** headlines (`bbc_headlines.csv`)
  - **The Guardian**
  - **Mayo Clinic** and **NIMH** on Seasonal Affective Disorder (SAD)
- We also found a dataset on **Kaggle** containing **weather sentiment from Tweets**.
- Additionally, we collected public data from **IDESCAT** related to Barcelona's local context.

Although this process gave us valuable insights, the data was either **too generic, unstructured, or not granular enough** (i.e., no daily city-level sentiment data).

### 2. Scope Refinement

We then refined our scope to focus on two specific cities:

- **Barcelona (Spain)**
- **Stockholm (Sweden)**

And aimed to compare **daily weather conditions** with **daily sentiment indicators** over a specific time period.

### 3. Final Approach – Country-level Sentiment API

To resolve the limitations in the previous data sources, we found an API that provided **daily sentiment scores by country**, based on Twitter data. This API returned values between 0 and 1, reflecting the average sentiment of posts each day.

This solution allowed us to obtain **consistent**, **scalable**, and **relevant** data for our analysis.

---

## 📊 Results

Based on our analysis:

- In **Spain**, we observed a **moderate positive correlation** between **temperature and sentiment**.
- In **Sweden**, **no significant correlation** was found between temperature and sentiment.
- **Precipitation and cloud cover** did **not** show a strong influence on mood in either country.

These results suggest that warmer weather in Spain may be associated with improved collective mood, whereas weather may not have the same psychological impact in Sweden, possibly due to cultural or environmental adaptation.

---

## 🗂️ Repository Structure

```text
weather-and-mood/
│
├── data/
│   ├── weather_data.csv
│   ├── sentiment_data.csv
│   ├── bbc_headlines.csv
│   ├── reddit_rss_sentiment.csv
│   └── kaggle_twitter_sentiment.csv
│
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_data_merge.ipynb
│   └── 03_analysis.ipynb
│
├── scraping/
│   └── twitter_scraper.py  # Deprecated due to low tweet volume
│
├── README.md
├── requirements.txt
└── .gitignore
