# 🏅 Olympic Data Analysis

An exploratory data analysis project using historical **Summer Olympic Games data** (1896–2016) to analyze athlete participation, countries, sports, events, and medal performance.

> **Dataset**: `athlete_events.csv` (271,116 records) + `noc_regions.csv` for NOC-to-region mapping  
> **Focus**: Summer Olympics only (222,552 records after filtering)

---

## 📌 Project Overview

The objective of this project is to explore historical Olympic athlete-event data and answer analytical questions related to:

- Olympic participation trends over time
- Countries and regions performance
- Athlete demographics (age, height, weight)
- Sports and event analysis
- Medal tally by country and year
- Top-performing athletes
- Male vs. female participation and medal achievements

---

## 🎯 Key Analyses Performed

| Analysis | Description |
|---|---|
| **Medal Tally** | Country-wise gold, silver, bronze and total medals |
| **Overall Stats** | Total editions, cities, sports, athletes, nations |
| **Participation Trends** | Nations and events growth over Olympic years |
| **Top Athletes** | Most successful athletes overall and by country |
| **Country-wise Analysis** | Medal performance per country per year |
| **Age Distribution** | Age of athletes and medalists |
| **Height & Weight** | Physical attributes across sports |
| **Gender Participation** | Male vs. female trends over time |

---

## 🔍 Key Insights

### 🌍 Overall Summary
- **28 Olympic editions** covered (1896–2016)
- **23 host cities** across the globe
- **52 sports** featured across all editions
- **63,414 unique athletes** participated
- **206 unique countries/regions** represented
- After removing duplicates, **221,167** clean athlete-event records were analyzed

### 🥇 Medal Tally Highlights
- **USA dominates** the all-time medal tally with **1,035 Gold, 802 Silver, 708 Bronze = 2,545 total medals** — by far the most of any country
- **Russia (URS/RUS)** is a distant second with **592 Gold, 498 Silver, 487 Bronze = 1,577 total**
- **Germany** comes third with **444 Gold, 457 Silver, 491 Bronze = 1,392 total**
- **UK** and **France** round out the top 5 with 895 and 777 total medals respectively
- Many countries have participated but never won a medal (e.g., Vanuatu, Yemen, Madagascar)

### 📈 Participation Growth Over Time
- The first modern Olympic Games in **1896 had just 12 countries** participating
- Participation grew steadily to **204 countries in 2016**
- Notable dip in 1980 (80 countries) due to the **boycott of the Moscow Olympics**
- Sharp jump from 1988 (156) to 1992 (168) after the fall of the Berlin Wall

### 🏃 Events Growth
- Events grew from **43 in 1896** to **306 in 2016** — a 7× increase
- Major growth spurts occurred post-WWII and again in the 1990s–2000s
- 2016 Rio Olympics had the most events ever at that point (306)

### 🎯 Country-Specific Insight
- **India in 2016**: Won 0 Gold, 1 Silver, 1 Bronze = **2 total medals** (indicating India's room for improvement at the global stage)

### 📊 Medal Distribution
- In Summer Olympics dataset:
  - **Gold**: 11,456 medals awarded
  - **Bronze**: 11,409 medals awarded
  - **Silver**: 11,212 medals awarded
- Distribution is roughly equal across all three medal types

---

## 📂 Datasets

### 1. `athlete_events.csv`

Contains Olympic athlete participation and event-level information.

| Column | Description |
|---|---|
| `ID` | Athlete identifier |
| `Name` | Athlete name |
| `Sex` | Athlete gender (M/F) |
| `Age` | Athlete age |
| `Height` | Athlete height (cm) |
| `Weight` | Athlete weight (kg) |
| `Team` | Team name |
| `NOC` | National Olympic Committee code |
| `Games` | Olympic Games (e.g., "2016 Summer") |
| `Year` | Olympic year |
| `Season` | Olympic season (Summer/Winter) |
| `City` | Host city |
| `Sport` | Sport category |
| `Event` | Specific event |
| `Medal` | Medal won (Gold/Silver/Bronze/NaN) |

### 2. `noc_regions.csv`

Provides region/country information associated with NOC codes.

The notebook merges this dataset with the athlete-event data:

```python
df = df.merge(region_df, on='NOC', how='left')
```

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Python** | Core programming language |
| **Pandas** | Data manipulation and analysis |
| **NumPy** | Numerical operations |
| **Matplotlib** | Static data visualization |
| **Seaborn** | Statistical visualizations |
| **Plotly Express** | Interactive charts and line plots |
| **Jupyter Notebook** | Development environment |

---

## 📊 Methodology

### Data Preprocessing Steps

1. **Load Data** — Read `athlete_events.csv` and `noc_regions.csv`
2. **Filter Season** — Keep only Summer Olympics records
3. **Merge** — Join with region data on `NOC` column
4. **Remove Duplicates** — Dropped 1,385 duplicate rows
5. **Encode Medals** — One-hot encoded Medal column into Bronze/Gold/Silver columns (integers)
6. **Medal Tally** — Deduplicated by `Team, NOC, Games, Year, Sport, Event, Medal, Season` before aggregating
7. **Visualize** — Interactive Plotly line charts + static Seaborn/Matplotlib plots

### Key Functions Built

```python
def fetch_medal_tally(year, country):
    """
    Returns medal tally filtered by year and/or country.
    - 'Overall' for year → aggregate across all years
    - 'Overall' for country → aggregate across all countries
    """
```

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/Hrithik08raj/Olympic-Data-Analysis.git
   cd Olympic-Data-Analysis
   ```

2. Install required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Olympic_Analysis.ipynb
   ```

4. Ensure `athlete_events.csv` and `noc_regions.csv` are in the same directory.

---

## 📁 Project Structure

```
Olympic-Data-Analysis/
│
├── Olympic_Analysis.ipynb    # Main analysis notebook
├── README.md                 # Project documentation
├── athlete_events.csv        # Primary dataset (not included — download from Kaggle)
└── noc_regions.csv           # NOC to region mapping (not included — download from Kaggle)
```

> **Data Source**: [120 Years of Olympic History: Athletes and Results](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) on Kaggle

---

## 👤 Author

**Hrithik Raj**  
GitHub: [@Hrithik08raj](https://github.com/Hrithik08raj)
