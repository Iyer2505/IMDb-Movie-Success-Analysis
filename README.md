# IMDb Movie Success Analysis: Revenue, Ratings & Genre Trends

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Power%20BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![Machine%20Learning](https://img.shields.io/badge/Machine%20Learning-Regression-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

This project analyzes IMDb movie data to understand the key factors that influence movie success. The analysis explores the relationship between movie revenue, IMDb ratings, audience votes, critic scores, genres, directors, runtime, and release year.

The project combines **Exploratory Data Analysis**, **Machine Learning**, and an **interactive Power BI dashboard** to identify patterns in movie performance and predict revenue using available movie attributes.

The goal is to understand what drives a movie’s commercial and critical success.

---

## 🎯 Business Problem

Movie success depends on several factors such as audience rating, critic score, genre, director, votes, and release year. However, high-rated movies do not always generate high revenue, and high-grossing movies are not always critically acclaimed.

This project answers the question:

> What factors contribute most to a movie’s commercial and critical success?

---

## 🧠 Project Objectives

The main objectives of this project are to:

- Analyze movie revenue and IMDb rating patterns
- Identify top-performing movies by revenue and rating
- Understand genre-level performance trends
- Compare audience ratings with critic scores
- Analyze director performance
- Explore yearly trends in movie performance
- Build a machine learning model to predict movie revenue
- Create a Power BI dashboard for business storytelling

---

## 🗂️ Dataset Description

The dataset contains IMDb movie information including movie title, genre, director, actors, release year, runtime, IMDb rating, votes, revenue, and metascore.

### Key Columns

| Column | Description |
|---|---|
| `Title` | Movie title |
| `Genre` | Movie genre or multiple genres |
| `Director` | Movie director |
| `Actors` | Main cast |
| `Year` | Movie release year |
| `Runtime (Minutes)` | Movie duration |
| `Rating` | IMDb audience rating |
| `Votes` | Number of IMDb votes |
| `Revenue (Millions)` | Movie revenue in millions |
| `Metascore` | Critic score |

---

## 🛠️ Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- Jupyter Notebook
- Power BI

---

## 📂 Project Structure

```text
IMBD Data/
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
│   ├── actual_vs_predicted_revenue.png.png
│   ├── dashboard_director_performance.png.png
│   ├── dashboard_executive_overview.png.png
│   ├── dashboard_genre_audience.png.png
│   ├── dashboard_ml_prediction.png.png
│   ├── feature_importance.png.png
│   └── model_performance_rmse.png.png
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🔍 Exploratory Data Analysis

The EDA phase focuses on understanding the movie dataset, cleaning missing values, creating useful features, and answering key business questions.

### Business Questions

1. Which movies generated the highest revenue?
2. Which movies received the highest IMDb ratings?
3. What is the relationship between IMDb rating and revenue?
4. Do movies with more votes generate higher revenue?
5. Which genres perform best by rating and revenue?
6. How do critic scores compare with audience ratings?
7. Which directors consistently produce successful movies?
8. How have movie ratings and revenues changed over time?

---

## 🧹 Data Cleaning & Feature Engineering

The data preparation process included:

- Standardizing column names
- Handling missing values in revenue and metascore
- Creating missing-value indicator columns
- Splitting multi-genre movies into individual genre records
- Creating a genre bridge table for Power BI analysis
- Creating rating and revenue categories
- Creating machine learning-ready features

### Engineered Features

| Feature | Description |
|---|---|
| `primary_genre` | First listed genre of each movie |
| `genre_count` | Number of genres assigned to a movie |
| `movie_age` | Age of movie based on release year |
| `title_length` | Length of movie title |
| `director_movie_count` | Number of movies by the director in the dataset |
| `rating_category` | Grouped IMDb rating category |
| `revenue_category` | Grouped revenue category |

---

## 🤖 Machine Learning Model

A regression model was developed to predict movie revenue using available movie attributes.

### Machine Learning Objective

> Predict movie revenue based on features such as IMDb rating, votes, runtime, metascore, release year, genre, and director-related attributes.

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

- MAE — Mean Absolute Error
- RMSE — Root Mean Squared Error
- R² Score

---

## 📊 Model Performance

The best-performing model was:

```text
Gradient Boosting Regressor
```

| Metric | Value |
|---|---:|
| MAE | 40.48 million |
| RMSE | 79.44 million |
| R² Score | 0.52 |

The model explains approximately **52% of the variation in movie revenue** using the available dataset features.

Revenue prediction remains challenging because important business factors such as production budget, marketing spend, release strategy, franchise strength, and distribution scale are not included in the dataset.

---

## 📈 Machine Learning Visualizations

### Model Performance by RMSE

![Model Performance](IMBD%20Data/images/model_performance_rmse.png.png)

### Actual vs Predicted Revenue

![Actual vs Predicted Revenue](IMBD%20Data/images/actual_vs_predicted_revenue.png.png)

### Feature Importance

![Feature Importance](IMBD%20Data/images/feature_importance.png.png)

---

## 📊 Power BI Dashboard

An interactive Power BI dashboard was created to communicate the analysis and machine learning results in a business-friendly format.

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

## 🖼️ Dashboard Preview

### Executive Overview

![Executive Overview](IMBD%20Data/images/dashboard_executive_overview.png.png)

### Genre & Audience Insights

![Genre and Audience Insights](IMBD%20Data/images/dashboard_genre_audience.png.png)

### Director & Movie Performance

![Director and Movie Performance](IMBD%20Data/images/dashboard_director_performance.png.png)

### ML Revenue Prediction

![ML Revenue Prediction](IMBD%20Data/images/dashboard_ml_prediction.png.png)

---

## 💡 Key Insights

- Movies with higher audience votes tend to generate higher revenue.
- High IMDb ratings do not always guarantee high revenue.
- Revenue is strongly influenced by audience engagement, visibility, and genre.
- Critic scores and IMDb ratings show a positive relationship, but they do not always align perfectly.
- Some genres perform better commercially, while others perform better critically.
- Director performance is more reliable when evaluated using both average rating and movie count.
- The machine learning model achieved moderate predictive performance, showing that revenue can be partially estimated from available movie attributes.

---

## 🚀 Business Recommendations

Based on the analysis:

- Use audience engagement metrics such as votes as an important signal for commercial success.
- Analyze genre performance separately for revenue and ratings because commercial and critical success may differ.
- Evaluate directors based on both average rating and number of movies to avoid misleading conclusions.
- Use predictive modeling as a decision-support tool, not as the only decision-making method.
- Improve future revenue prediction by adding budget, production company, release month, country, franchise status, and marketing-related data.

---

## ⚠️ Project Limitations

This dataset does not include several important factors that can strongly influence movie revenue, such as:

- Production budget
- Marketing spend
- Release month
- Country or region
- Streaming availability
- Franchise status
- Production company
- Number of theaters
- Global box office performance

Because of these missing variables, the machine learning model should be interpreted as an analytical support model rather than a complete revenue forecasting system.

---

## ▶️ How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/bhargavimv27/IMDb-Movie-Success-Analysis.git
cd IMDb-Movie-Success-Analysis
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

For Windows:

```bash
venv\Scripts\activate
```

For macOS/Linux:

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Notebooks

```bash
jupyter notebook
```

Run the notebooks in this order:

```text
notebooks/01_data_cleaning_eda.ipynb
notebooks/02_machine_learning_model.ipynb
```

### 6. Open the Power BI Dashboard

Open the Power BI file:

```text
dashboard/imdb_movie_success_dashboard.pbix
```

If needed, update the data source paths in Power BI to point to:

```text
data/processed/
```

---

## 🔮 Future Improvements

Potential improvements for this project include:

- Add movie budget data
- Include release month and seasonality
- Add production company and country information
- Use external box office datasets
- Try advanced models such as XGBoost or LightGBM
- Deploy the model as a simple web app
- Publish the Power BI dashboard online

---

## ✅ Project Status

Completed:

- Data cleaning
- Exploratory data analysis
- Feature engineering
- Machine learning model development
- Power BI dataset preparation
- Power BI dashboard
- Dashboard screenshots
- GitHub-ready documentation

---

## 👤 Author

**Raghavendra Marghashayam Venkatesh**

---
