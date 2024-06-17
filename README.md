# Taxi Pickup Prediction in New York City

## Overview
This repository contains the code and documentation for predicting the number of taxi pickups in New York City. Given location coordinates (latitude and longitude) and time, the task is to predict the number of pickups in the query region and surrounding regions. The project utilizes data collected from January to March 2015 to predict the pickups for the same period in 2016. 

The primary error metric used for evaluation is Mean Absolute Percentage Error (MAPE).

## Contents

1. [Introduction](#introduction)
2. [Data Preparation](#data-preparation)
3. [Feature Engineering](#feature-engineering)
4. [Modeling](#modeling)
   - Baseline Model
   - Exponential Averages Forecasting
   - XGBoost Regression
   - SGD Implementation of Linear Regression
   - Random Forest Regression
   - Simple Linear Regression
5. [Performance Metrics](#performance-metrics)
6. [Workflow](#workflow)
7. [Conclusion and Future Work](#conclusion-and-future-work)
8. [References](#references)

## Introduction
The problem statement involves predicting the number of taxi pickups in an area in New York City in the upcoming 10 minutes. This prediction helps in understanding demand patterns and optimizing resource allocation.

## Data Preparation
The data preparation phase includes:
1. **Data Cleaning**: Handling outliers in latitude and longitude to ensure they fall within the bounds of New York City.
2. **Consistency Checks**: Ensuring time consistency, and validating fare, speed, and distance data.
3. **Time Binning**: Data is binned into 10-minute intervals, based on observations that it typically takes a driver around 10 minutes to switch to nearby areas for pickups.
4. **Sectional Division**: New York City is divided into 40 sections for more granular analysis.

## Feature Engineering
Feature engineering involves:
1. **Moving Ratios (Average and Exponential)**: Forecasting methods based on moving averages and exponential averages.
2. **Fourier Feature Transformation**: Incorporating Fourier transformation along with exponential smoothing and Holt's winter seasonal adjustments.
3. **Recent Pickup History**: Including features based on the last five pickups to capture recent trends.

## Modeling
### Baseline Model
- **Train MAPE**: 14.87

### Exponential Averages Forecasting
- **Train MAPE**: 14.12

### XGBoost Regression
- **Train MAPE**: 8.52

### SGD Implementation of Linear Regression
- **Train MAPE**: 1.02

### Random Forest Regression
- **Train MAPE**: 8.25

### Simple Linear Regression
- **Train MAPE**: 8.59

## Performance Metrics
The Mean Absolute Percentage Error (MAPE) was used to evaluate the performance of each model. The models showed varying levels of accuracy, with the SGD implementation of linear regression achieving the lowest MAPE.

## Workflow
1. **Data Acquisition and Cleaning**: Collect and clean the data to ensure quality and consistency.
2. **Time Binning and Sectional Division**: Organize the data into 10-minute bins and divide New York City into 40 sections.
3. **Feature Engineering**: Generate relevant features including moving averages, Fourier transformations, and recent pickup history.
4. **Model Training**: Train various models and evaluate their performance using MAPE.
5. **Evaluation and Selection**: Select the best-performing models based on MAPE scores.

## Conclusion and Future Work
The project successfully predicted taxi pickups with varying degrees of accuracy using different regression models. The best results were achieved using the SGD implementation of linear regression, closely followed by random forest and simple linear regression. Future work could involve:
- Further improving model accuracy through advanced feature engineering.
- Exploring deep learning models for better predictions.
- Implementing real-time prediction pipelines for practical use.

## References
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Pandas Documentation](https://pandas.pydata.org/)

This README.md file provides a comprehensive overview of the project, including data preparation, feature engineering, modeling, and future work. For detailed code and notebooks, please refer to the corresponding directories in this repository.
