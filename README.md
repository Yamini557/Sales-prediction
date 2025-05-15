# Walmart Sales Forecasting using Prophet

This repository contains code for forecasting Walmart sales using the Prophet library by Facebook.

## Overview

The goal of this project is to predict future sales based on historical data provided by Walmart. The analysis involves data loading, preprocessing, and time series forecasting using the Prophet model.

## Libraries Used

-   pandas
-   prophet
-   matplotlib
-   seaborn

## Data Sources

The data used in this project comes from the Walmart Sales Forecasting Kaggle competition and includes the following CSV files:

-   `train.csv`: Historical sales data.
-   `features.csv`: Additional features related to the stores and dates.
-   `stores.csv`: Information about each store.

These files are expected to be located in the `/kaggle/input/walmart-sales-forecast/` directory.

## Code Description

The Python script performs the following steps:

1.  **Imports necessary libraries.**
2.  **Loads the CSV files** (`train.csv`, `features.csv`, `stores.csv`) into pandas DataFrames.
3.  **Merges the DataFrames** into a single DataFrame (`df`) based on common columns.
4.  **Converts the 'Date' column** to datetime objects and sorts the DataFrame by date.
5.  **Aggregates the weekly sales** by date to get the total daily sales across all stores and departments.
6.  **Renames the 'Date' and 'Weekly\_Sales' columns** to 'ds' and 'y' respectively, as required by Prophet.
7.  **(Optional) Applies a log transformation** to the 'y' column to stabilize variance (commented out in the provided code).
8.  **Initializes and fits the Prophet model**, including yearly and weekly seasonality. Daily seasonality is turned off.
9.  **Creates a future dataframe** for the next 90 days.
10. **Makes predictions** using the fitted Prophet model.
11. **Visualizes the forecast** using Prophet's built-in plotting functions.
12. **Plots the forecast components** (trend, yearly seasonality, weekly seasonality).
13. **Compares the actual sales** (from the training data) with the predicted sales.

