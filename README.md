# IMDb Movie Success Analysis: Revenue, Ratings & Genre Trends

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Regression-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Project Overview

This project analyzes IMDb movie data to understand the key factors that influence movie success. The analysis explores relationships between movie revenue, IMDb ratings, audience votes, critic scores, genres, directors, runtime, and release year.

The project includes three major components:

1. Exploratory Data Analysis using Python
2. Machine Learning model to predict movie revenue
3. Interactive Power BI dashboard for business insights

The goal is to transform raw movie data into actionable insights that can support decisions around movie performance, audience engagement, genre strategy, and revenue forecasting.

---

## Business Problem

Movie performance is influenced by multiple factors such as genre, audience ratings, critic scores, votes, runtime, and director history. However, high ratings do not always guarantee high revenue, and high revenue does not always indicate strong critical success.

This project investigates:

> What factors contribute most to a movie's commercial and critical success?

---

## Objectives

The main objectives of this project are to:

- Analyze movie revenue and rating patterns
- Identify top-performing movies by revenue and IMDb rating
- Understand genre-level trends in revenue, ratings, and audience engagement
- Compare audience ratings with critic scores
- Analyze director performance
- Explore yearly trends in movie performance
- Build a machine learning model to predict movie revenue
- Create a Power BI dashboard to communicate insights clearly

---

## Dataset

The dataset contains IMDb movie information including movie title, genre, director, actors, release year, runtime, IMDb rating, votes, revenue, and metascore.

### Key Columns

| Column | Description |
|---|---|
| `Title` | Movie title |
| `Genre` | Movie genre or multiple genres |
| `Director` | Movie director |
| `Actors` | Main cast |
| `Year` | Release year |
| `Runtime (Minutes)` | Movie duration |
| `Rating` | IMDb audience rating |
| `Votes` | Number of IMDb votes |
| `Revenue (Millions)` | Movie revenue in millions |
| `Metascore` | Critic score |

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- Power BI
- Jupyter Notebook

---

## Project Structure

```text
IMDb-Movie-Success-Analysis/
│
├── data/
│   ├── raw/
│   │   └── IMDB-Movie-Data.csv
│   │
│   └── processed/
│       ├── fact_movies.csv
│       ├── bridge_movie_genre.csv
│       ├── dim_genre.csv
│       ├── genre_summary.csv
│       ├── director_summary.csv
│       ├── yearly_summary.csv
│       ├── model_performance.csv
│       ├── feature_importance.csv
│       └── actual_vs_predicted_revenue.csv
│
├── notebooks/
│   ├── 01_data_cleaning_eda.ipynb
│   └── 02_machine_learning_model.ipynb
│
├── dashboard/
│   └── imdb_movie_success_dashboard.pbix
│
├── images/
│   ├── dashboard_executive_overview.png
│   ├── dashboard_genre_audience.png
│   ├── dashboard_director_performance.png
│   ├── dashboard_ml_prediction.png
│   ├── model_performance_rmse.png
│   ├── actual_vs_predicted_revenue.png
│   └── feature_importance.png
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Exploratory Data Analysis

The EDA focuses on identifying important patterns in movie performance.

### Key Business Questions

1. Which movies generated the highest revenue?
2. Which movies received the highest IMDb ratings?
3. What is the relationship between IMDb rating and revenue?
4. Do movies with more votes generate higher revenue?
5. Which genres perform best by rating and revenue?
6. How do critic scores compare with audience ratings?
7. Which directors consistently produce successful movies?
8. How have movie ratings and revenues changed over time?

### Data Cleaning & Feature Engineering

The data preparation process included:

- Standardizing column names
- Handling missing values in revenue and metascore
- Creating missing-value indicator columns
- Splitting multi-genre movies into separate genre records
- Creating a genre bridge table for dashboard analysis
- Creating rating and revenue categories
- Creating additional features for machine learning

Engineered features include:

- `primary_genre`
- `genre_count`
- `movie_age`
- `title_length`
- `director_movie_count`
- `rating_category`
- `revenue_category`

---

## Machine Learning Model

A regression model was built to predict movie revenue using movie-related attributes.

### ML Objective

> Predict movie revenue based on available features such as IMDb rating, votes, runtime, metascore, release year, genre, and director-related attributes.

### Target Variable

```text
Revenue (Millions)
```

### Models Used

Three regression models were compared:

1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

### Evaluation Metrics

The models were evaluated using:

- MAE: Mean Absolute Error
- RMSE: Root Mean Squared Error
- R² Score

### Best Performing Model

The best model was:

```text
Gradient Boosting Regressor
```

Model performance:

| Metric | Value |
|---|---:|
| MAE | 40.48 million |
| RMSE | 79.44 million |
| R² Score | 0.52 |

The model explains approximately 52% of the variation in movie revenue using the available dataset features.

### Model Interpretation

Revenue prediction is challenging because major revenue drivers such as production budget, marketing spend, release strategy, franchise strength, distribution scale, and release season are not included in the dataset.

Even with these limitations, the model provides useful insight into which available features are most associated with revenue performance.

---

## Power BI Dashboard

An interactive Power BI dashboard was created to communicate the analysis and machine learning results.

### Dashboard Pages

The dashboard includes four pages:

1. Executive Overview
2. Genre & Audience Insights
3. Director & Movie Performance
4. ML Revenue Prediction

### Dashboard Features

- KPI cards for total movies, total revenue, average rating, average revenue, average metascore, and total votes
- Revenue and rating trends by year
- Top movies by revenue and IMDb rating
- Genre-level revenue and rating analysis
- Audience vote analysis
- Director performance analysis
- Model performance comparison
- Actual vs predicted revenue analysis
- Feature importance visualization

---

## Dashboard Preview

Replace these image paths with your actual exported Power BI screenshots after building the dashboard.

### Executive Overview

![Executive Overview](IMBD_Data/images/dashboard_executive_overview.png)

### Genre & Audience Insights

![Genre and Audience Insights](images/dashboard_genre_audience.png)

### Director & Movie Performance

![Director and Movie Performance](images/dashboard_director_performance.png)

### ML Revenue Prediction

![ML Revenue Prediction](images/dashboard_ml_prediction.png)

---

## Key Insights

- Movies with higher audience votes tend to generate higher revenue.
- High IMDb ratings do not always guarantee high revenue.
- Revenue is influenced by audience engagement, genre, and visibility.
- Critic scores and IMDb ratings show a positive relationship, but they do not always align perfectly.
- Some genres perform better commercially, while others perform better critically.
- Director-level analysis shows that consistent performance is better evaluated when directors have multiple movies in the dataset.
- The machine learning model achieved moderate predictive performance, showing that revenue can be partially estimated from available movie attributes.

---

## Business Recommendations

Based on the analysis:

- Use audience engagement metrics such as votes as an important signal for commercial success.
- Analyze genre performance separately for revenue and ratings because commercial and critical success may differ.
- Evaluate directors based on both average rating and number of movies to avoid misleading conclusions.
- Use predictive modeling as a support tool, not a final decision-maker, because key financial variables such as budget and marketing spend are missing.
- Improve future revenue prediction by adding budget, production company, release month, country, franchise status, and marketing-related data.

---

## How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/IMDb-Movie-Success-Analysis.git
cd IMDb-Movie-Success-Analysis
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

For Windows:

```bash
venv\Scripts\activate
```

For macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Notebooks

Open Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebooks in this order:

```text
notebooks/01_data_cleaning_eda.ipynb
notebooks/02_machine_learning_model.ipynb
```

### 5. Open the Power BI Dashboard

Open the Power BI file:

```text
dashboard/imdb_movie_success_dashboard.pbix
```

If needed, update the data source paths inside Power BI to point to the CSV files in:

```text
data/processed/
```

---

## Future Improvements

Potential improvements for this project include:

- Adding movie budget data
- Including release month and seasonality
- Adding production company and country information
- Using external box office datasets
- Testing advanced models such as XGBoost or LightGBM
- Deploying the model as a small web app
- Publishing the Power BI dashboard online

---

## Project Status

Completed:

- Data cleaning
- Exploratory data analysis
- Feature engineering
- Machine learning model development
- Power BI dataset preparation
- Dashboard design plan

To finalize:

- Add Power BI `.pbix` file
- Export dashboard screenshots
- Update dashboard preview images in this README

