<div align="center">

# 🌍 World Countries Data Analysis
### Exploring 195 Countries with Python & Pandas
#### Population &nbsp;|&nbsp; Democracy &nbsp;|&nbsp; Economy &nbsp;|&nbsp; Energy &nbsp;|&nbsp; Health

<br/>

![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Numpy](https://img.shields.io/badge/NumPy-1.x-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

<br/>

> **A comprehensive Exploratory Data Analysis (EDA) of world countries — covering population, democracy, economy, energy, and health across 6 continents.**

</div>

---

## 🌐 Project Overview

This project performs **Exploratory Data Analysis** on a rich dataset of world countries. The dataset contains **60+ features** per country — from GDP and inflation to democracy scores, energy production, and political leadership.

The analysis answers real-world questions like:
- Which country is the most populous? The least?
- Which nations score highest on democracy?
- How many countries have "Republic" in their official name?
- Which African country leads in population?

---

## 🗂️ Project Structure

```
world-countries-analysis/
│
├── 📓 Countries.ipynb     # Main analysis notebook
├── 📄 Countries.csv       # Dataset — 195 countries, 60+ features
└── 📘 README.md           # You're here!
```

---

## 📦 Dataset Overview

| Property | Detail |
|----------|--------|
| **Rows** | ~195 countries |
| **Columns** | 60+ features |
| **Source** | World Bank / aggregated global data |

**Feature Categories:**

| Category | Features |
|----------|----------|
| 🌍 Geography | `region`, `continent`, `latitude`, `longitude`, `land_area` |
| 👥 Demographics | `population`, `birth_rate`, `death_rate`, `fertility_rate`, `median_age` |
| 💰 Economy | `gdp`, `inflation`, `unemployment_pct`, `tax_revenue_pct_gdp` |
| ⚡ Energy | `electricty_production_coal_pct`, `renewable_energy_consumption_pct` |
| 🏥 Health | `health_expenditure_pct_gdp`, `life_expectancy`, `suicide_rate` |
| 🗳️ Politics | `democracy_score`, `democracy_type`, `political_leader`, `title` |

---

## 🔍 Analysis Questions Answered

```python
# 1. Most & Least Populated Countries
df[df["population"] == df["population"].max()]["country"]
df[df["population"] == df["population"].min()]["country"]

# 2. Top 5 Most Democratic Countries
df.sort_values(by="democracy_score", ascending=False)["country"].head()

# 3. How many distinct regions exist?
df["region"].value_counts().count()

# 4. Countries in Eastern Europe
df[df["region"] == "Eastern Europe"]["country"]

# 5. Political leader of 2nd most populous country
df[df["population"] == df["population"].nlargest(2).iloc[1]]["political_leader"]

# 6. Countries with unknown political leaders
df[df["political_leader"].isna()]["country"].count()

# 7. Countries with "Republic" in their name
# → Custom function using .apply() + string matching

# 8. Most populous country in Africa
africa_df = df[df["continent"] == "Africa"]
africa_df[africa_df["population"] == africa_df["population"].max()]["country"]
```

---

## 💡 Interesting Findings

| 🔎 Question | 🌍 Answer |
|-------------|-----------|
| Most Populated Country | China / India |
| Least Populated Country | Vatican City / Nauru |
| Most Democratic Region | Northern/Western Europe |
| Countries with "Republic" | 100+ nations worldwide |
| Most Populous African Country | Nigeria |

---

## 🛠️ Key Pandas Techniques Used

- `df.shape` & `df.info()` — dataset structure inspection  
- `df.describe()` — statistical summary of all numeric columns  
- **Boolean filtering** — `df[df["col"] == value]` for targeted queries  
- `sort_values()` + `head()` — ranking and top-N analysis  
- `value_counts().count()` — counting unique categories  
- `nlargest()` + `iloc[]` — fetching Nth largest values  
- `isna()` — finding missing / unknown data  
- `.apply()` with custom functions — string pattern matching  
- **Continent-level filtering** — subsetting data by region/continent  

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/your-username/world-countries-analysis.git
cd world-countries-analysis

# Install dependencies
pip install pandas numpy jupyter

# Launch notebook
jupyter notebook Countries.ipynb
```

---

## 🧠 Skills Demonstrated

- ✅ **Exploratory Data Analysis (EDA)** — systematic dataset investigation
- ✅ **Data Filtering** — multi-condition boolean indexing
- ✅ **Aggregation & Ranking** — `sort_values`, `nlargest`, `value_counts`
- ✅ **Handling Missing Data** — detecting NaN values with `isna()`
- ✅ **Custom Functions with `.apply()`** — string search across rows
- ✅ **Subset Analysis** — continent/region-level filtering
- ✅ **Real-world Domain Knowledge** — geography, politics, economics

---

## 📊 Sample Dataset Snapshot

| Country | Continent | Population | GDP (USD) | Democracy Score | Democracy Type |
|---------|-----------|------------|-----------|-----------------|----------------|
| Afghanistan | Asia | 41,128,771 | 14.5B | 2.97 | Authoritarian |
| Albania | Europe | 2,775,634 | 18.8B | 5.98 | Hybrid Regime |
| Algeria | Africa | 44,903,225 | 191.9B | 3.50 | Authoritarian |
| Andorra | Europe | 79,824 | 3.3B | — | Unknown |

---


