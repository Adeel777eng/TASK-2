# TASK-2
# Predict Future Stock Prices (Short-Term)

## Objective

The objective of this task is to **predict the next day’s closing stock price** using historical stock data. This project involves fetching data from Yahoo Finance, selecting meaningful features, and applying machine learning regression models to evaluate performance and visualize predictions.

---

## Dataset Used

- **Source:** [Yahoo Finance](https://finance.yahoo.com/)
- **Ticker:** `TSLA` (Tesla Inc.)
- **Fetched Using:** `yfinance` Python library
- **Date Range:** January 1, 2022 – December 31, 2024
- **File Format:** Fetched live as a DataFrame (not stored in a local `.csv`)

### Features Used:
- `Open` – Opening price of the day
- `High` – Highest price during the day
- `Low` – Lowest price during the day
- `Volume` – Total shares traded

### Target:
- **Next day’s closing price**, created using `data['Close'].shift(-1)`


## Tools and Libraries

- `yfinance` – For downloading stock data
- `pandas`, `numpy` – For data manipulation
- `matplotlib` – For plotting
- `scikit-learn` – For machine learning models and evaluation


## Models Applied

Two regression models were trained and evaluated:

1. **Linear Regression**
2. **Random Forest Regressor** (100 trees, random_state=42)


## Key Steps

1. Fetch historical stock data using `yfinance`
2. Shift the 'Close' column to create the next-day prediction target
3. Select features: `Open`, `High`, `Low`, `Volume`
4. Split the dataset into training and testing sets (80/20)
5. Train both Linear Regression and Random Forest models
6. Evaluate model performance using **R² Score** and **RMSE**
7. Plot predicted vs actual closing prices


## Results

| Model                  | Metric         | Value (Example)     |
|------------------------|----------------|---------------------|
| Linear Regression      | R² Score       | ~0.85 – 0.90        |
|                        | RMSE           | Moderate             |
| Random Forest Regressor| R² Score       | ~0.95+              |
|                        | RMSE           | Lower than LR       |

 **Random Forest Regressor** consistently outperformed Linear Regression in terms of accuracy and error.

## Visualization

A line plot compares the actual vs predicted closing prices for the first 50 test samples. Both models follow the trend well, with Random Forest offering a closer fit.


## File Structure
- Fetched from live data frame.

