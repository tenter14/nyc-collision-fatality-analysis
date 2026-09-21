# nyc-collision-fatality-analysis
Logistic Regression &amp; Random Forest analysis of ~66,000 NYC motor vehicle collision records to model crash fatality rates by vehicle make, driver profile, and contributing factors.
# NYC Motor Vehicle Collision Fatality Analysis

**Tools:** Python · PyCharm · Scikit-learn · Pandas · Matplotlib · Seaborn  
**Methods:** Logistic Regression · Random Forest · Exploratory Data Analysis

---

## Overview

This project investigates whether certain vehicle makes — specifically Ford — are associated with a higher likelihood of fatal outcomes in New York City motor vehicle collisions. Using a dataset of approximately 66,000 crash records, we built classification models to predict crash fatality and identify the key variables driving fatal outcomes.

The central question: **Does driving a Ford increase crash fatalities?**

---

## Dataset

- **Source:** NYC Open Data — Motor Vehicle Collisions
- **Size:** ~66,000 crash records
- **Dependent Variable (DV):** Fatal outcome — Die / No Die (binary)
- **Independent Variables (IV):**
  - Vehicle Make — Ford (Y/N)
  - Driver Gender — Male / Female
  - Contributing Factor (e.g., driver inattention, unsafe speed)
  - Vehicle Year
  - Number of Vehicle Occupants
  - Number of People Injured
  - Licensed Status of Driver

---

## Methodology

### 1. Data Cleaning & Preprocessing
- Filtered and standardized vehicle make labels
- Encoded categorical variables (gender, licensed status, contributing factors)
- Handled missing values and class imbalance

### 2. Exploratory Data Analysis (EDA)
- Analyzed death distribution by vehicle brand (Top 4 + Other)
- Mapped top 10 contributing factors associated with fatalities
- Plotted deaths vs. injuries by vehicle brand
- Analyzed Ford fatalities by vehicle year (current vs. prior year)

### 3. Modeling

**Logistic Regression**

Log Odds of Fatal Crash = β₀ + β₁·Ford(Y/N) + β₂·Male(Y/N) + β₃·Contributing Factors + β₄·Vehicle Year + β₅·Vehicle Occupants + β₆·Number of People Injured + β₇·Licensed Status

**Random Forest**
- Used as a non-linear complement to logistic regression
- Assessed variable importance to confirm key predictors

---

## Key Findings

| Insight | Detail |
|---|---|
| Ford's share of crash fatalities | ~18% (nearly 1 in 5 recorded deaths) |
| Ford fatality rate vs. other makes | ~2.1x higher |
| Top contributing factor | Unspecified (54% of deaths) |
| Distraction-related fatalities | 14% |
| Speed-related fatalities | 8% |

**Important:** These results reflect observed rates, not causal relationships. Ford vehicles are more common in NYC, and omitted variables (driver age, road type, weather conditions) may explain the difference. **Correlation does not imply causation.**

---

## Repository Structure

```
nyc-collision-fatality-analysis/
│
├── data/
│   └── README.md               # Data source info and download instructions
│
├── notebooks/
│   └── collision_analysis.py   # Main analysis script
│
├── outputs/
│   ├── death_distribution.png  # Death distribution by vehicle brand
│   ├── contributing_factors.png
│   └── deaths_vs_injuries.png
│
├── README.md
└── requirements.txt
```

---

## Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
```

Install with:
```bash
pip install -r requirements.txt
```


## How to Run

1. Clone the repository
```bash
git clone https://github.com/[YourUsername]/nyc-collision-fatality-analysis.git


2. Download the NYC Motor Vehicle Collisions dataset from [NYC Open Data](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95) and place it in the `/data` folder

3. Run the analysis
```bash
python notebooks/collision_analysis.py


