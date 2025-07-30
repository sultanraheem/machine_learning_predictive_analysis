# Video Game Sales Prediction Project

## Contributors
Sultan Raheem, Rob Molenda, Muneeb Samad, and Ivan Cherniavskyi

---

## Problem Statement

We explore the video game industry with a focus on **predicting future sales**. Accurate forecasting is critical for developers, publishers, and marketers. Our objective is to build a machine learning model that predicts future video game sales based on historical trends and economic indicators such as:

- Genre  
- Platform  
- Region  
- Release timing  
- GDP  
- Population demographics

---

## Datasets

All datasets are in `.csv` format and located in the `data/` folder.

### GDP Dataset

**Overview:**  
Annual GDP data for countries (1960–2023), sourced from the World Bank.

**Structure:**  
- **Entries:** 266  
- **Columns:**  
  - `Country Name`  
  - `Country Code`  
  - `Indicator Name`  
  - `Indicator Code`  
  - `Years (1960–2023)`

**Usage:**  
Used to assess how economic growth impacts video game sales.

---

### Population Dataset

**Overview:**  
Annual population data by country (1960–2023), also from the World Bank.

**Structure:**  
- **Entries:** 306  
- **Columns:**  
  - `Country Name`  
  - `Country Code`  
  - `Indicator Name`  
  - `Indicator Code`  
  - `Years (1960–2023)`

**Usage:**  
Focuses on the 15–64 age group — the primary gaming demographic — to estimate market size and sales potential.

---

### Video Game Sales Dataset

**Overview:**  
Detailed sales data across games, platforms, and regions. Sourced from Kaggle.

**Structure:**  
- **Entries:** 16,598  
- **Columns:**  
  - `Rank`, `Name`, `Platform`, `Year`, `Genre`, `Publisher`  
  - `NA_Sales`, `EU_Sales`, `JP_Sales`, `Other_Sales`, `Global_Sales`

**Usage:**  
Used to uncover trends in global and regional sales by genre, platform, and publisher.

---

## Visualization & Data Analysis

Located in: `visualization.ipynb`

### Dependencies

```bash
pip install pandas matplotlib seaborn plotly wordcloud
Key Visualizations
Top-Selling Games: Bar chart of top 10 games globally

Top-Selling Publishers: Bar chart by publisher

Sales by Genre: Comparative analysis across genres

Platform Popularity: Line chart over time

Word Cloud Illustration: Most common game words

Interactive Pie Charts: Sales breakdown by region

Interactive Histograms: Sales/genre distribution by platform

Boxplots: Distribution by region, genre, platform, and year

Regional Sales Heatmap: Sales visualization across regions

Statistical Analysis
Descriptive Stats: Mean, median, mode for all sales columns

Range: Sales range from minimal to 82.73M units

Variance: 2.45

Standard Deviation: 1.57

IQR: 0.42

All findings are supported with visualizations and tables

Key Findings
Genre Popularity: Sports dominates, followed by Role-Playing and Platform genres

Platform Evolution: Rise/fall of Wii, NES, PlayStation series

Regional Preferences: Japan favors Role-Playing; North America prefers Sports/Action

Sales Variability: Large disparity between top-selling games and the average

Data Preprocessing
Located in: data_prep.ipynb

Features
Video Game Sales Data
Missing Year: Filled with median

Missing Publisher: Filled with mode

Type Conversion: Year converted to integer

Storage: Stored as data table in games_data.sqlite

GDP Data
Cleaned: Dropped unnecessary columns

Transposed: Converted to long format

Aggregated: Summed GDP per year

Storage: Stored as gdp table

Population Data
Cleaned: Similar steps as GDP

Mean Calculated: For each year across all countries

Storage: Stored as population table

Requirements
bash
Copy
Edit
pip install pandas sqlite3
How to Use
Place vgsales.csv, GDP.csv, and Population.csv in the correct directory

Run data_prep.ipynb

Output: games_data.sqlite with tables:

data

gdp

population

Modeling
Located in: modelling.ipynb

Workflow
Data Loaded: From games_data.sqlite

Inspection: Dataset preview and basic stats

Cleaning: Null handling, type fixes

Feature Engineering: Normalized sales, GDP/population ratios

Models Tested:

Linear Regression:

R²: Low

MSE: High

Decision Tree Regression:

Slightly better R², still poor

Neural Network (TensorFlow):

R² still unsatisfactory

High MSE

Evaluation Summary
Low R² across all models

High MSE, indicating large prediction errors

Predictive models underperformed

Potential Causes
Limited Features: Lacked behavioral/marketing data

Data Quality: Missing/incomplete values

Model Complexity: More advanced models or different techniques may be needed

Prerequisites
bash
Copy
Edit
pip install pandas numpy sqlite3 scikit-learn tensorflow matplotlib
Usage
Prepare your environment and place SQLite database in the correct path

Run modelling.ipynb step by step

Review R² and MSE outputs to assess model performance

Conclusion
This project developed a full pipeline for video game sales forecasting, including data acquisition, visualization, preprocessing, and predictive modeling.

Despite thorough analysis, the models did not perform well, highlighting:

The complexity of sales prediction

The need for more comprehensive and granular features

Opportunities for further research in feature engineering, data augmentation, and alternative modeling techniques
