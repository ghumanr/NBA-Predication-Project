# NBA Player Performance Analysis (2025 Season)

## Overview

The project focuses on:

* Cleaning and preprocessing raw player totals data
* Engineering per-game and efficiency metrics
* Computing advanced shooting statistics
* Creating a weighted synthetic performance line
* Preparing structured datasets for further modeling

This project was initially developed and tested locally using CSV data exports.

I am currently working on integrating full web-scraping functionality so the data can be dynamically pulled and updated instead of relying on manually downloaded datasets.

---

## Project Structure

```
├── dataset/
│   ├── Player Totals.csv
│   ├── Player_Totals_Cleaned.csv
│   └── Player_Totals_Cleaned_lst56avg.csv
│
├── final_project_complete_notebook.ipynb
├── final_project_webscraper.py
└── README.md
```

---

## Data Processing Workflow

### 1. Data Cleaning

* Renamed columns for readability
* Removed unused fields (Birth Year, League, etc.)
* Filtered for:

  * 2025 season
  * Minimum games started
  * Minimum points per game
* Handled missing values
* Replaced zero games to prevent division errors

### 2. Feature Engineering

Created advanced metrics such as:

* Points Per Game
* Field Goals Attempted Per Game
* Free Throws Per Game
* Three Point Attempts Per Game
* True Shooting Percentage
* Last 5 Games Average Points

### 3. Synthetic Performance Line

A custom weighted metric was built to approximate short-term scoring projections:

```
synthetic_line =
    0.6 * Last_5_Games_Points_Avg
  + 0.3 * Points_Per_Game
  + 0.1 * efficiency_component
```

This combines:

* Recent performance
* Season averages
* Shooting efficiency

---

## Technologies Used

* Python 3
* Pandas
* Matplotlib
* Custom Web Scraper Module
* Jupyter Notebook

---

## Current Development Status

This project was originally built using locally stored CSV data.

I am currently working on:

* Implementing automated web scraping
* Dynamically pulling updated player stats
* Removing the dependency on manually downloaded datasets
* Making the project fully reproducible from raw web data

The goal is to transition this from a local analysis project into a fully automated data pipeline.

---

## Future Improvements
* Automate scraping for:

  * Player game logs
  * Rolling averages
  * Advanced efficiency stats
* Add predictive modeling (regression / ML)
* Build a lightweight dashboard
* Add model evaluation metrics
* Deploy as a web app

---

## How to Run

1. Clone the repository
2. Install dependencies:

```
pip install pandas matplotlib
```

3. Run the notebook:

```
jupyter notebook final_project_complete_notebook.ipynb
```

---



