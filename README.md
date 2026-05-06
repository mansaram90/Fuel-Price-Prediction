# Fuel Price Prediction

This project explores UK fuel price data and builds machine learning models to predict fuel prices.

The aim of this project is not only to build a prediction model, but also to practise the full data science workflow. This includes loading data, cleaning it, doing exploratory data analysis, finding useful insights, training different models, comparing model performance, and explaining the results clearly.

## Project Overview

Fuel prices can vary by fuel type, brand, station location, motorway status, and whether a station belongs to a supermarket. In this project, I used historical fuel price data and station information to understand these patterns and predict fuel prices.

The project includes:

- Data loading and inspection
- Data cleaning
- Exploratory data analysis
- Feature engineering
- Baseline modelling
- Ridge Regression
- Random Forest
- XGBoost
- Model comparison
- Error analysis
- Portfolio-style insights and conclusions

## Dataset

The project uses two CSV files:

- `price_history.csv`
- `stations.csv`

The price history file contains fuel price records over time.

The stations file contains information about fuel stations, including brand, location, postcode, motorway status, and supermarket status.

After loading both datasets, they are joined together so that each price record also has station-level information.

## Main Questions Explored

This project tries to answer questions such as:

- Which fuel types are the most expensive?
- Do motorway stations charge more?
- Are supermarket stations cheaper?
- Which brands have higher or lower average prices?
- How do prices change over time?
- Which features are useful for predicting fuel prices?
- Which machine learning model performs best?

## Data Cleaning

The data was checked for:

- Missing values
- Duplicate records
- Incorrect data types
- Unrealistic fuel prices
- Inconsistent station information

Some fuel prices were clearly unrealistic, such as values that were too low or too high. These were treated as outliers and removed before modelling.

This step is important because bad data can strongly affect the performance of machine learning models.

## Exploratory Data Analysis

The EDA section looks at patterns in the data using summary statistics and visualisations.

Some areas explored include:

- Average price by fuel type
- Average price by brand
- Motorway vs non-motorway stations
- Supermarket vs non-supermarket stations
- Price trends over time
- Station distribution by region and brand

The EDA helped build an understanding of the dataset before training models.

## Key Insights

Some of the main insights from the analysis were:

- Fuel type is one of the strongest drivers of price.
- Motorway stations tend to be more expensive than non-motorway stations.
- Supermarket stations are often slightly cheaper than other stations.
- Brand and location also influence price.
- Tree-based models perform better than linear models for this dataset.

These insights are useful because they explain not just what the model predicts, but also why prices may vary.

## Modelling Approach

The target variable is fuel price.

The models were trained using features such as:

- Fuel type
- Brand
- Motorway flag
- Supermarket flag
- Time-based features
- Station location information

Categorical variables were encoded so they could be used by machine learning models.

The data was split into training and test sets so the models could be evaluated on unseen data.

## Models Trained

The following models were compared:

### Baseline Model

The baseline model predicts the average price from the training data.

This gives a simple benchmark. Any useful machine learning model should perform better than this baseline.

### Ridge Regression

Ridge Regression is a regularised linear model.

It is useful as a simple and interpretable model, but it may struggle when the relationship between features and fuel price is not fully linear.

### Random Forest

Random Forest is a tree-based ensemble model.

It can capture non-linear relationships and interactions between features, which makes it more suitable for this type of data.

### XGBoost

XGBoost is a gradient boosting model.

It often performs very well on structured tabular data and was included to compare against Random Forest and Ridge Regression.

## Model Evaluation

The models were evaluated using:

- MAE, Mean Absolute Error
- RMSE, Root Mean Squared Error
- R² Score

MAE is useful because it shows the average prediction error in pence per litre.

RMSE gives more penalty to larger errors.

R² shows how much of the variation in fuel prices is explained by the model.

## Model Comparison

The model comparison showed that tree-based models performed better than the linear model.

Example results from the notebook:

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| XGBoost | 3.718 | 5.473 | 0.910 |
| Random Forest | 3.809 | 5.527 | 0.908 |
| Ridge Regression | 13.793 | 15.887 | 0.242 |
| Baseline | 17.157 | 18.727 | -0.054 |

XGBoost gave the best performance, with Random Forest very close behind.

The results show that non-linear models are better at capturing the patterns in fuel prices.

## Best Model

The best model in this project was XGBoost.

It had the lowest error and the highest R² score.

This suggests that it was better able to capture relationships between fuel price, fuel type, station brand, location, motorway status, supermarket status, and time-based features.

## Error Analysis

After selecting the best model, prediction errors were analysed to understand where the model performed well and where it struggled.

This included checking:

- Actual vs predicted prices
- Distribution of prediction errors
- Cases where the model made larger mistakes

Error analysis is important because a model should not only have good overall scores, but should also be understood in terms of its limitations.

## What I Explored

This project helped me practise:

- Loading and combining multiple datasets
- Cleaning real-world data
- Handling outliers
- Creating useful features
- Performing EDA
- Building baseline and machine learning models
- Comparing model performance
- Interpreting results
- Writing a project in a portfolio-friendly way

It also showed that model performance depends heavily on data quality and feature selection.

## How to Run the Project

Clone the repository:

```bash
git clone <your-repository-link>
cd fuel-price-prediction
