# Credit-Spread-Forecasting


This project implements an advanced system for credit spread prediction using machine learning techniques and market regime analysis. The system combines data from various financial sources and uses models such as Random Forest and XGBoost with early stopping to optimize predictions.

## Key Features

- **Multi-source Analysis**: Integration of data from FRED, Yahoo Finance, TED Rate, and economic policy indicators
- **Causal Feature Engineering**: Generation of temporal features such as lags and moving averages
- **Advanced Models**:
  - Random Forest with custom early stopping
  - XGBoost with Bayesian optimization
  - Market regime analysis using Hidden Markov Models
- **Robust Preprocessing**: Management of skewness and data standardization

## Requirements

```python
numpy
pandas
scikit-learn
xgboost
hmmlearn
factor_analyzer
pandas_datareader
yfinance
statsmodels
seaborn
matplotlib
scikit-optimize
```

## Project Structure

- `CommonConfig`: Configuration class for dates, time series, and paths
- `CommonDataLoader`: Management of data loading from different sources
- `EarlyStoppingRandomForest`: Custom implementation of Random Forest with early stopping
- `ModelTuner`: Hyperparameter optimization for Random Forest and XGBoost
- `MarketRegimeAnalyzer`: Market regime analysis using HMM

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

```python
# Configuration and data loading
config = CommonConfig()
loader = CommonDataLoader(config)

# Loading data from different sources
fred_data = loader.fetch_fred_data()
yahoo_data = loader.fetch_yahoo_data()
ted_rate = loader.load_tedrate()
policy_data = loader.load_policy_data()

# Feature engineering and preprocessing
df = feature_engineering_causale(df)
df = reduce_skew(df, feature_cols)
train_df, test_df = preprocess_data(train_df, test_df, feature_cols)

# Training models
rf_model = EarlyStoppingRandomForest()
xgb_model = XGBRegressor()
```

## Model Features

### Random Forest with Early Stopping
- Dynamic performance monitoring
- Automatic optimization of tree numbers
- Validation on dedicated set

### XGBoost with Bayesian Optimization
- Optimal hyperparameter search
- Early stopping on validation set
- Automatic overfitting management

### Market Regime Analysis
- Automatic regime identification
- Transition matrix calculation
- Optimization of state numbers

## Contributing

You are welcome to contribute to the project. To do so:
1. Fork the repository
2. Create a branch for your modifications
3. Submit a pull request

## License

This project is distributed under the MIT license.
