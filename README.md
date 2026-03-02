# Predict-Future-Stock-Prices

## Task Objective
The goal of this project is to build a machine learning pipeline that predicts the **next day's closing price** of a stock. By using historical data (Open, High, Low, and Volume), the model attempts to learn price patterns and provide a forecast for the following trading session.

## Dataset Used
The data is dynamically pulled from the **Yahoo Finance API** using the `yfinance` library.
* **Ticker Symbol:** `AAPL` (Apple Inc.)
* **Period:** January 1, 2020, to January 1, 2024.
* **Features:** * `Open`: Starting price of the day.
    * `High/Low`: Price range during the session.
    * `Volume`: Total number of shares traded.
* **Target Variable:** `Next_Close` (The closing price of the subsequent day).

## Models Applied
We implemented the **Random Forest Regressor** from the `scikit-learn` library. 
* **Type:** Ensemble Learning (Multiple Decision Trees).
* **Data Split:** 80% Training / 20% Testing.
* **Validation:** We used a chronological split (`shuffle=False`) to ensure the model was tested on "future" data it hadn't seen during training, mimicking real-world trading.

## Key Results and Findings
1.  **Trend Following:** The model successfully captured the overall bullish (upward) and bearish (downward) trends of the stock over the 4-year period.
2.  **The Lag Effect:** A key observation was that the model often predicts a price close to the current day's price, creating a "lag" in the visualization during sharp price spikes.
3.  **Performance Metric:** The model's accuracy was measured using **Mean Squared Error (MSE)** and **R-Squared**, providing a quantitative look at how many dollars the prediction was "off" on average.

### How to Run
1. Install dependencies: `pip install yfinance pandas matplotlib scikit-learn`
2. Open the Jupyter Notebook.
3. Run all cells to fetch data, train the model, and generate the prediction graph.
