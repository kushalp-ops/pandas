# IPL Dataset Analysis & Data Cleaning

This repository contains Exploratory Data Analysis (EDA) and data preprocessing on the IPL (Indian Premier League) matches dataset (`matches.csv`) covering seasons from 2008 to 2024 using Pandas.

---

## 📌 Dataset Overview

* **Dataset Name:** `matches.csv`
* **Initial Shape:** 1,095 rows × 20 columns
* **Final Cleaned Shape:** 1,028 rows × 19 columns
* **Target Domain:** Sports Analytics / Cricket Analytics

---

## 🛠️ Key Data Exploration Steps

1. **Environment Setup & Data Ingestion**
   * Installed and imported `pandas`.
   * Loaded the dataset into a DataFrame `df`.

2. **Data Inspection**
   * Displayed top 5 (`df.head()`) and bottom 5/10 (`df.tail()`) rows.
   * Inspected column names (`df.columns`) and dataset dimensions (`df.shape`).
   * Evaluated column data types, non-null counts, and memory usage (`df.info()`).
   * Calculated descriptive summary statistics for numerical fields (`df.describe()`).

3. **Data Cleaning & Preprocessing**
   * **Duplicates Check:** Checked for duplicated rows using `df.duplicated().sum()`.
   * **Feature Dropping:** Removed the uninformative column `method` which contained 1,074 missing values (`df.drop(columns='method', inplace=True)`).
   * **Missing Value Handling:** Identified null counts across features (`df.isnull().sum()`) and dropped missing records using `df.dropna(inplace=True)`.

---

## 📊 Dataset Schema

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `id` | `int64` | Unique match identifier |
| `season` | `str` | IPL season/year |
| `city` | `str` | City where the match was played |
| `date` | `str` | Match date |
| `match_type` | `str` | Stage of tournament (e.g., League, Qualifier, Final) |
| `player_of_match` | `str` | Awardee for Player of the Match |
| `venue` | `str` | Stadium/venue name |
| `team1` | `str` | First playing team |
| `team2` | `str` | Second playing team |
| `toss_winner` | `str` | Team winning the coin toss |
| `toss_decision` | `str` | Toss decision (`bat` or `field`) |
| `winner` | `str` | Match winning team |
| `result` | `str` | Win type (`runs` or `wickets`) |
| `result_margin` | `float64` | Win margin |
| `target_runs` | `float64` | Target set for second innings |
| `target_overs` | `float64` | Target overs available |
| `super_over` | `str` | Super over flag (`Y`/`N`) |
| `umpire1` | `str` | On-field umpire 1 |
| `umpire2` | `str` | On-field umpire 2 |

---

## 🚀 Quickstart Guide

```python
import pandas as pd

# Load dataset
df = pd.read_csv("matches.csv")

# Perform Data Cleaning
df.drop(columns=["method"], inplace=True)
df.dropna(inplace=True)

# View summary statistics
print(df.describe())
