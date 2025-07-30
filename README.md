# Video Game Sales Prediction Project

# Contributors  
Sultan Raheem, Rob Molenda, Muneeb Samad, and Ivan Cherniavskyi

# Problem Statement

We explore the video game industry with a focus on **predicting future sales**. Accurate forecasting is critical for developers, publishers, and marketers. Our objective is to build a machine learning model that predicts future video game sales based on historical trends and economic indicators such as:

# Key Factors  
- Genre  
- Platform  
- Region  
- Release timing  
- GDP  
- Population demographics

# Datasets

All datasets are in `.csv` format and located in the `data/` folder.

## GDP Dataset

### Overview  
Annual GDP data for countries (1960–2023), sourced from the World Bank.

### Structure  
- Entries: 266  
- Columns:  
  - Country Name  
  - Country Code  
  - Indicator Name  
  - Indicator Code  
  - Years (1960–2023)

### Usage  
Used to assess how economic growth impacts video game sales.

## Population Dataset

### Overview  
Annual population data by country (1960–2023), also from the World Bank.

### Structure  
- Entries: 306  
- Columns:  
  - Country Name  
  - Country Code  
  - Indicator Name  
  - Indicator Code  
  - Years (1960–2023)

### Usage  
Focuses on the 15–64 age group — the primary gaming demographic — to estimate market size and sales potential.

## Video Game Sales Dataset

### Overview  
Detailed sales data across games, platforms, and regions. Sourced from Kaggle.

### Structure  
- Entries: 16,598  
- Columns:  
  - Rank, Name, Platform, Year, Genre, Publisher  
  - NA_Sales, EU_Sales, JP_Sales, Other_Sales, Global_Sales

### Usage  
Used to uncover trends in global and regional sales by genre, platform, and publisher.

# Visualization & Data Analysis

Located in: visualization.ipynb

## Dependencies

pip install pandas matplotlib seaborn plotly wordcloud

## Key Visualizations

- Top-Selling Games: Bar chart of top 10 games globally  
- Top-Selling Publishers: Bar chart by publisher  
- Sales by Genre: Comparative analysis across genres  
- Platform Popularity: Line chart over time  
- Word Cloud Illustration: Most common game words  
- Interactive Pie Charts: Sales breakdown by region  
- Interactive Histograms: Sales/genre distribution by platform  
- Boxplots: Distribution by region, genre, platform, and year  
- Regional Sales Heatmap: Sales visualization across regions  

# Statistical Analysis

- Descriptive Stats: Mean, median, mode for all sales columns  
- Range: Sales range from minimal to 82.73 million units  
- Variance: 2.45  
- Standard Deviation: 1.57  
- Interquartile Range (IQR): 0.42  

Visualizations and tables support these findings.

# Key Findings

- Genre Popularity: Sports dominates, followed by Role-Playing and Platform genres  
- Platform Evolution: Rise and fall of Wii, NES, PlayStation series  
- Regional Preferences: Japan favors Role-Playing; North America prefers Sports and Action  
- Sales Variability: Large disparity between top-selling games and the average  

# Data Preprocessing

Located in: data_prep.ipynb

## Features

### Video Game Sales Data  
- Filled missing values in Year with median  
- Filled missing values in Publisher with mode  
- Converted Year column to integer  
- Stored cleaned data in SQLite table data

### GDP Data  
- Dropped unnecessary columns  
- Transposed to long format  
- Summed GDP per year  
- Stored aggregated data in SQLite table gdp

### Population Data  
- Similar cleaning as GDP data  
- Calculated mean population per year  
- Stored aggregated data in SQLite table population

## Requirements

pip install pandas sqlite3

## How to Use

1. Place vgsales.csv, GDP.csv, and Population.csv in the working directory  
2. Run data_prep.ipynb  
3. The cleaned data will be saved in games_data.sqlite with tables:  
   - data  
   - gdp  
   - population  

# Modeling

Located in: modelling.ipynb

## Workflow

1. Load data from games_data.sqlite  
2. Inspect datasets and calculate summary statistics  
3. Handle missing values and fix data types  
4. Engineer new features for model inputs  
5. Train and evaluate models:

### Linear Regression  
- R²: Low  
- MSE: High  

### Decision Tree Regression  
- Slightly better R², but still poor  
- High MSE  

### Neural Network (TensorFlow)  
- R² remained unsatisfactory  
- High MSE  

## Evaluation Summary

- All models had low R² scores, indicating poor fit  
- High MSE values show large prediction errors  
- Predictive accuracy was inadequate

## Possible Reasons for Poor Performance

- Limited feature set (lack of marketing, quality, or consumer behavior data)  
- Data quality issues such as missing or inconsistent data  
- Model complexity may need enhancement or different approaches  

# Prerequisites

pip install pandas numpy sqlite3 scikit-learn tensorflow matplotlib

# Usage Instructions

1. Ensure all required libraries are installed  
2. Place games_data.sqlite in your working directory  
3. Run modelling.ipynb or the Python scripts step-by-step  
4. Review output metrics (R², MSE) to evaluate model performance  

# Conclusion

This project covers a complete pipeline for video game sales forecasting — from data gathering and cleaning to visualization and modeling.

Despite comprehensive efforts, the predictive models underperformed, underscoring:

- The complexity inherent in forecasting video game sales  
- The necessity for additional features and better data quality  
- Opportunities for further model refinement and feature engineering
