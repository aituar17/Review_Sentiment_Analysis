# 📱 Review_Sentiment_Analysis

## 📌 Project Overview
This project analyzes **10,000 Google Play Store reviews** of the LinkedIn Android app (US, English only).
I collected reviews using the `google-play-scraper` package, applied sentiment analysis with **VADER (NLTK)**, and visualized user sentiment trends.

The goal is to understand **user sentiment patterns**, identify **pain points**, and highlight how sentiment aligns with **star ratings and time**.

## 📊 Dataset
- **Source:** [Google Play Store](https://play.google.com/store/apps/details?id=com.linkedin.android&pli=1)
- **App:** LinkedIn (Android)
- **Scope:** 10,000 reviews (🇺🇸 US, English only)
- **Fields collected:** `reviewId`, `userName`, `rating`, `date`, `review`, `developer reply`, `country`
- **Tools:** `google-play-scraper` Python package
⚠️ Raw data is excluded from GitHub for size/privacy.

## 🛠️ Methodology
1. **Data Collection** (`01_collect_reviews.ipynb`)
    - Scraped reviews via Google Play API for 5 countries
    - Deduplicated and cleaned text
2. **Sentiment Analysis** (`02_sentiment_analysis.ipynb`)
    - Pre-processed reviews (removed links, special chars, etc.)
    - Applied **NLTK VADER** sentiment analyzer
    - Classified reviews into `positive`, `neutral`, `negative`
3. **Top Words Analysis** (`03_top_words_by_country.ipynb`)
    - Tokenized and lemmatized text
    - Removed stopwords and app-specific boilerplate terms (`linkedin`, `app`, `login`)
    - Identified top words by **(country, sentiment)**
  
## 📈 Results & Insights
### Overall Sentiment Distribution
- The majority of reviews are **positive**, but a notable portion are **negative**, often mentioning login, crashes, and notifications.

### Sentiment by Country
- **US & UK:** Similar distribution, majority positive
- **Italy:** Higher share of negative reviews, often about access/login
- **Finland:** Fewer reviews, but more neutral/positive
- **Kazakhstan:** Small sample, skewed toward negative (login/verification issues)

#### Visuals:
##### Sentiment Distribution
![Sentiment Distribution](images/sentiment_distribution.png)

##### Sentiment Distribution by Country
![Sentiment Distribution by Country](images/sentiment_dist_by_country.png)

## 💡 Business Implications
- **Login/verification issues** remain a global frustration.
- **Positive reviews** highlight LinkedIn’s networking and job search features.
- **Regional differences** suggest targeted improvements (e.g., stability in Italy, smoother sign-ins in Kazakhstan).

## ⚖️ Limitations & Next Steps
- Reviews are **self-selected** → may not represent all users.
- Language bias: scraping was in English, so some Italian/Kazakh reviews may be underrepresented.
- Future extensions:
    - Multi-language sentiment models
    - Topic modeling (LDA/BERT) for deeper insights
    - Time-series analysis of sentiment trends
 
## ⚙️ Installation
Clone this repository and install dependencies:

```bash
git clone https://github.com/aituar17/Review_Sentiment_Analysis.git
cd Review_Sentiment_Analysis
pip install -r requirements.txt
```

⚠️ To reproduce: you must scrape reviews yourself (01_collect_reviews.ipynb) because raw data is not stored in the repo.

## 📂 Project Structure
