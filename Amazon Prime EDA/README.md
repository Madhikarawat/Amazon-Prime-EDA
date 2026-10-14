# 🎬 Amazon Prime TV Shows & Movies: Exploratory Data Analysis

An end-to-end Exploratory Data Analysis (EDA) of Amazon Prime Video's content library using Python. The project cleans and merges two datasets, engineers new features, calculates business KPIs, and presents 17 visualizations that turn raw data into content-strategy insights.
---

## 📌 Problem Statement

Streaming platforms like Amazon Prime Video host thousands of titles across genres, countries and age groups. The information is spread over many attributes (ratings, runtime, cast, genres), which makes it hard to see clear patterns. This project explores that library to find trends and the factors linked to ratings, popularity and global reach.

## 🎯 Business Objective

Support data-driven content strategy by understanding:
- What the content mix looks like (movies vs shows, genres, countries, age ratings)
- How content and ratings have changed over time.
- Which genres, cast and crew are associated with higher audience ratings.
- Whether popularity and ratings are related.

---

## 📂 Dataset

| File | Rows | Columns | Description |
|------|------|---------|-------------|
| `titles.csv` | 9,871 | 15 | Title details: type, release year, runtime, genres, production countries, age certification, seasons, IMDb and TMDB scores/votes/popularity |
| `credits.csv` | 124,235 | 5 | Cast and crew: person, character, role (Actor / Director) |

> Add your dataset source link here (e.g., Kaggle).

---

## 🛠️ Tools & Libraries

- **Python**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Others**: `ast` (parsing list-like columns), Jupyter Notebook

---

## 🔄 Project Workflow

### 1. Understanding the Data
- Inspected shape, data types, statistical summary and unique values for both datasets
- Checked for duplicates (3 in titles, 56 in credits) and missing values

### 2. Data Wrangling
- Filled missing `age_certification` with **"Not Rated"**
- Filled missing `imdb_score` with the column mean
- Dropped duplicate rows from both datasets
- Merged `titles` and `credits` on `id` (left join)

### 3. Feature Engineering
- `decade`: release decade from release year
- `runtime_category`: Short / Medium / Long
- `is_movie`: binary flag (1 = movie, 0 = show)
- `imdb_category`: Poor / Average / Good / Excellent

### 4. KPI Calculation
- **Content overview**: type split, release year range (1912–2022), average IMDb score
- **Genres**: most frequent genres and highest-rated genres (genre lists parsed and exploded into one row per genre)
- **Ratings**: IMDb vs TMDB averages and correlation
- **Cast & crew**: most frequent actors and directors
- **Countries**: top production countries
- **Age certification**: distribution of certifications
- **Popularity**: correlation between TMDB popularity and IMDb score
- **Trends**: releases per year and average IMDb score per year

### 5. Data Visualization (17 charts)
Movies vs shows, releases per year, runtime distribution, top genres, genre ratings, IMDb score distribution, IMDb vs TMDB scatter, top actors, top directors, role distribution, top countries, certification distribution, rating by certification, popularity vs IMDb, runtime trend over time, runtime vs IMDb score.

---

## 🔍 Key Findings

- **Genres**: Drama, comedy, thriller, action and romance are the most common genres on the platform.
- **Highest-rated genres**: Documentation, history, reality, war and animation have the highest average IMDb scores.
- **Countries**: The US leads content production, followed by GB, IN (India), CA and FR.
- **Ratings agreement**: IMDb and TMDB scores show a moderate-to-strong positive correlation (**0.62**).
- **Popularity vs quality**: TMDB popularity has almost no correlation with IMDb score (**0.07**), so popular titles are not necessarily the best rated.
- **Average rating**: The average IMDb score across the library is about **5.97**.
- **Time span**: The library covers 1912 to 2022, with a large increase in releases in the late 2010s.
- **Age certification**: A large share of titles have no certification, and R and PG-13 are the most common among rated titles.

---

## 💡 Business Recommendations

1. Invest in high-volume genres (drama, comedy, thriller) while promoting high-rated niches such as documentaries and history.
2. Collaborate with frequently featured and successful directors and actors.
3. Use IMDb and TMDB ratings to power personalized recommendations.
4. Keep a balanced mix of new releases and classic titles to appeal to diverse audiences.
5. Expand content from strong regions (US, UK, India) and explore under-represented regions.

---

## 📁 Repository Structure

```
├── AmazonPrime_Analysis.ipynb   
├── titles.csv                  
├── credits.csv                  
└── README.md
```

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook AmazonPrime_Analysis.ipynb
```

Make sure `titles.csv` and `credits.csv` are in the same folder as the notebook.


## 🚀 Future Improvements

- Build an interactive dashboard in Power BI or Tableau
- Add text analysis of title descriptions
- Predict IMDb scores using a regression model
- Analyze seasons and episode counts for TV shows in more depth

