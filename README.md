# CodeAlpha Data Analytics Portfolio

&gt; A comprehensive collection of data analytics projects completed during the CodeAlpha internship, covering Exploratory Data Analysis, Data Visualization, and Natural Language Processing.

---

## Table of Contents

- [Portfolio Overview](#portfolio-overview)
- [Task 1: EDA — Medical Insurance Cost Analysis](#task-1-eda--medical-insurance-cost-analysis)
- [Task 2: Data Visualization — Global Poverty Dashboard](#task-2-data-visualization--global-poverty-dashboard)
- [Task 3: Sentiment Analysis — Facebook Reviews](#task-3-sentiment-analysis--facebook-reviews)
- [Technologies & Tools](#technologies--tools)
- [Author](#author)

---

## Portfolio Overview

This repository consolidates three distinct data analytics projects completed as part of the **CodeAlpha Data Analytics Internship**. Each project demonstrates a different core competency in the data analytics pipeline:

| # | Project | Domain | Key Skills |
|---|---------|--------|------------|
| 1 | Medical Insurance EDA | Healthcare / Finance | Python, Pandas, Matplotlib, Seaborn, Statistical Analysis |
| 2 | Global Poverty Dashboard | Socio-Economics / Development | Tableau, LOD Expressions, Dashboard Design, Geospatial Viz |
| 3 | Facebook Reviews Sentiment Analysis | NLP / Social Media | Python, Pandas, WordCloud, Regex, Text Mining |

---

## Task 1: EDA — Medical Insurance Cost Analysis

**Repository:** [CodeAlpha_Data_Analytics_Task2_EDA_Medical_Insurance](https://github.com/Riddhi712/CodeAlpha_Data_Analytics_Task2_EDA_Medical_Insurance)

### Overview
A comprehensive exploratory data analysis of a medical insurance cost dataset containing **7,500 customer records** across **16 variables**. The analysis investigates relationships between demographic factors, lifestyle choices, health indicators, and annual medical costs through advanced visualizations and statistical testing.

### Dataset Description
| Variable | Type | Description | Range/Values |
|----------|------|-------------|--------------|
| `customer_id` | String | Unique identifier | MIC100001 - MIC107500 |
| `age` | Integer | Customer age | 18 - 65 |
| `gender` | Categorical | Biological sex | Male, Female |
| `bmi` | Float | Body Mass Index | 16.0 - 45.0 |
| `children` | Integer | Dependent children | 0 - 5 |
| `smoker` | Categorical | Smoking status | Yes, No |
| `region` | Categorical | Geographic region | Northeast, Northwest, Southeast, Southwest, Central |
| `occupation` | Categorical | Employment type | Driver, Doctor, Teacher, Engineer, Nurse, Lawyer, etc. |
| `annual_income_usd` | Integer | Annual income | $18,000 - $176,977 |
| `exercise_level` | Categorical | Physical activity | Low, Moderate, High |
| `chronic_diseases` | Integer | Chronic conditions | 0 - 5 |
| `doctor_visits_per_year` | Integer | Annual physician visits | 0 - 15 |
| `hospitalizations_last_year` | Integer | Prior year admissions | 0 - 3 |
| `alcohol_consumption_per_week` | Integer | Weekly alcohol units | 0 - 14 |
| `insurance_plan` | Categorical | Coverage tier | Basic, Standard, Gold, Premium |
| `annual_medical_cost_usd` | Float | **Target variable** | $1,500 - $49,333 |

### Key Findings
- 🚬 **Smoking Impact:** Smokers average **$29,152** vs non-smokers **$15,170** — a **92% cost increase**
- 🏃 **Exercise Benefit:** High exercise reduces costs by **17.6%** ($19,563 → $16,110)
- 🏥 **Plan Tier Effect:** Gold plans show highest average costs ($23,559), suggesting adverse selection
- 📉 **Chronic Disease Prevalence:** 49.8% have zero chronic diseases; only 7 have 5+ conditions
- 🔗 **Strongest Correlation:** Smoker × Medical Cost (r = 0.73) — the dominant cost driver
- 💰 **Income Irrelevance:** Income shows negligible correlation (r = 0.02) with medical costs

### Visualizations
- Distribution charts (medical cost, age, BMI, income)
- Correlation matrix with heatmap
- Bivariate scatter analysis (age vs cost, BMI vs cost)
- Advanced segment analysis by region, occupation, and lifestyle
- Boxplots by chronic disease count

---

## Task 2: Data Visualization — Global Poverty Dashboard

**Repository:** [CodeAlpha_Data_Analytics_Task3_Data_Visualization](https://github.com/Riddhi712/CodeAlpha_Data_Analytics_Task3_Data_Visualization)

### Overview
A **Tableau-native dashboard** analyzing global poverty dynamics, child mortality, service access gaps, and GDP-poverty disconnects across regions and income groups. This portfolio analysis identifies high-impact investment opportunities in underserved markets.

### Dashboard Architecture
| Worksheet | Viz Type | Key Technique |
|-----------|----------|---------------|
| Poverty by Region | Diverging Bar | Fixed LOD + Color by Severity |
| Child Mortality Matrix | Highlight Table | Calculated Field for Severity × Income |
| Access to Service | Stacked Bar | Measure Names + Custom Sort |
| Time Trend | Dual-Axis Line | Synchronized Axes + Reference Band |
| Access Index Map | Symbol Map | Mapbox WMS + Sized Circles |
| GDP vs Poverty | Scatter Plot | Log Axis + Trend Line + Outlier Highlight |

### Tableau Techniques Used
- **LOD Expressions:** `{FIXED [Region] : AVG([Poverty Rate])}`
- **Calculated Fields:** Poverty Severity Rank, Access Index Normalized, GDP Per Capita Binning
- **Parameters:** `pSeverityParam` (multi-select), `pIncomeParam` (single-select radio)
- **Map Configuration:** Mapbox Streets v11 with custom WMS integration
- **Interactivity:** Cross-dashboard filtering across all six worksheets

### Key Insights
- Sub-Saharan Africa, Middle East, and South Asia show the highest poverty rates
- Extreme poverty correlates strongly with child mortality in low-income groups
- Service access (water, health, education) varies significantly by region
- GDP per capita shows disconnect from poverty rates in certain outlier countries

---

## Task 3: Sentiment Analysis — Facebook Reviews

**Repository:** [CodeAlpha_Data_-Analytics_Task_4_sentiment_analysis_Facebook_Review](https://github.com/Riddhi712/CodeAlpha_Data_-Analytics_Task_4_sentiment_analysis_Facebook_Review)

### Overview
A comprehensive sentiment analysis of **355,807+ Facebook Mobile App reviews** using Python, Pandas, and WordCloud visualization to understand user sentiment, identify key pain points, and track trends over time.

### Key Metrics
| Metric | Value |
|--------|-------|
| **Overall Sentiment** | Mildly Positive |
| **Average Rating** | **3.89/5** |
| **Positive Reviews** | ~70.3% |
| **Negative Reviews** | ~24.1% |
| **Recent Trend (May 2026)** | Strong negative shift — increasing user frustration |

### Major Issues Identified
| Issue | Frequency | User Sentiment |
|-------|-----------|---------------|
| Too many ads | Very High | Extremely Negative |
| Account suspensions/bans | High | High Anger |
| UI changes (bottom navigation) | High | Frustrated |
| Bugs & glitches | High | Annoyed |
| Storage bloat | Medium | Negative |

### Visualizations
- **Negative Reviews Word Cloud:** Highlights "ads", "problem", "video", "account", "update", "page"
- **Positive Reviews Word Cloud:** Highlights "good", "best", "nice", "love", "great", "excellent", "thank you"

### Files Included
- `facebook_sentiment_analysis.py` — Main analysis script
- `sentiment_wordclouds.png` — Generated visualization
- `sentiment_summary.csv` — Summary statistics

### How to Run
```bash
# Install dependencies
pip install pandas matplotlib wordcloud numpy

# Run the analysis
python facebook_sentiment_analysis.py
