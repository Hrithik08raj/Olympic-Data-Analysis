# 🏅 Olympic Data Analysis

An exploratory data analysis project using historical **Summer Olympic Games data** to analyze athlete participation, countries, sports, events, and medal performance.

The project uses Python to clean, transform, analyze, and visualize Olympic data and uncover meaningful patterns across different Olympic editions.

---

## 📌 Project Overview

The objective of this project is to explore historical Olympic athlete-event data and answer analytical questions related to:

- Olympic participation
- Countries and regions
- Athletes
- Sports and events
- Medal performance
- Country-wise medal trends
- Successful athletes
- Athlete age
- Athlete height and weight
- Male vs. female medal achievements

The analysis focuses specifically on the **Summer Olympics**.

---

## 🎯 Objectives

The main objectives of this project are:

- Clean and preprocess the Olympic dataset
- Filter the dataset to Summer Olympic Games
- Merge Olympic data with NOC-to-region information
- Handle duplicate records
- Analyze medal distributions
- Calculate country-wise medal tallies
- Analyze participation trends across Olympic editions
- Identify successful athletes
- Study athlete age and medal relationships
- Analyze height and weight among medalists
- Compare male and female medal achievements
- Create interactive and static visualizations

---

## 📂 Datasets

The project uses two datasets:

### 1. `athlete_events.csv`

Contains Olympic athlete participation and event-level information.

Important columns include:

| Column | Description |
|---|---|
| `ID` | Athlete identifier |
| `Name` | Athlete name |
| `Sex` | Athlete gender |
| `Age` | Athlete age |
| `Height` | Athlete height |
| `Weight` | Athlete weight |
| `Team` | Team name |
| `NOC` | National Olympic Committee code |
| `Games` | Olympic Games |
| `Year` | Olympic year |
| `Season` | Olympic season |
| `City` | Host city |
| `Sport` | Sport |
| `Event` | Event |
| `Medal` | Medal won |

### 2. `noc_regions.csv`

Provides region/country information associated with NOC codes.

The notebook merges this dataset with the athlete-event data using:

```python
df = df.merge(region_df, on='NOC', how='left')

🛠️ Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Plotly
Jupyter Notebook
