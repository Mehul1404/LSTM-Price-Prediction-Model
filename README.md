# Stock Price Prediction using LSTM

This project utilizes historical stock data of any listed stock to predict future stock prices using a Long Short-Term Memory (LSTM) neural network model. The project includes various analyses and visualizations of the stock data, as well as a stock price prediction model based on time-series data.

## Table of Contents

- [Overview](#overview)
- [Technologies Used](#technologies-used)
- [Data Description](#data-description)
- [Preprocessing](#preprocessing)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Visualizations](#visualizations)
- [Usage](#usage)


## Overview

This project aims to predict the stock prices of stocks using historical stock market data from Yahoo Finance. The data is processed, visualized, and then used to train an LSTM-based deep learning model to forecast future prices. The model outputs the predicted stock prices, which are visualized in both candlestick charts and line graphs for easy analysis.

## Technologies Used

- **Python 3.x**
- **Libraries**: 
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `plotly`
  - `tensorflow` (for building LSTM model)
  - `sklearn` (for data preprocessing)
  - `yfinance` (for data retrieval)
  - `mplfinance` (for candlestick charts)
  
## Data Description

The dataset is retrieved from Yahoo Finance using the `yfinance` package. The dataset includes the following columns:

- **Open**: The price at which the stock opens on a given day
- **High**: The highest price reached during the day
- **Low**: The lowest price reached during the day
- **Close**: The price at which the stock closes on a given day
- **Volume**: The number of shares traded
- **Dividends**: Dividend payouts
- **Stock Splits**: Any stock split events

The data spans from **2016-01-12** to the present.

## Preprocessing

The stock data undergoes several preprocessing steps:

1. **Handling Missing Data**: Missing data is filled using forward fill.
2. **Feature Engineering**: The data is resampled weekly and monthly for trend analysis.
3. **Normalization**: Data is normalized using MinMaxScaler to bring the values into a range of [-1, 1].
4. **Sequence Generation**: Stock prices are transformed into sequences with a specified length of 11 days to feed into the LSTM model.

## Model Training

A Sequential LSTM model is used for predicting future stock prices. The model is structured as follows:

- **Input Layer**: Accepts sequences of 11 days worth of stock price data
- **LSTM Layer 1**: LSTM with 64 units
- **LSTM Layer 2**: LSTM with 128 units
- **Dense Layer 1**: Dense layer with 50 units
- **Dense Layer 2**: Output layer with 1 unit representing the predicted price

The model is compiled with the **Adam optimizer** and **Mean Squared Error (MSE)** loss function.

## Evaluation

The model is evaluated using test data, and performance metrics such as loss and accuracy are recorded. The predicted prices are compared to the actual stock prices for the test set, and visualized to assess the model's performance.

## Visualizations

- **Correlation Heatmap**: Visualizes the correlation between different features of the stock data.
- **Boxplots**: Distribution of each stock attribute (Open, High, Low, Close, Volume, Dividends).
- **Time-Series Plots**: Plots of various stock attributes (Open, High, Low, Close, Volume) over time.
- **Candlestick Charts**: Plot the candlestick chart for visualizing stock price movements over time.
- **Predicted vs Actual Prices**: Visualizes the predicted stock prices against the actual values.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/stock-price-prediction.git
   cd stock-price-prediction

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt

3. Run the script:
   ```bash
   python stock_prediction.py

4. The output will include:
  - **Stock Data Visualizations**
- **Stock price predictions**
- **Evaluation metrics**

