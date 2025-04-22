# Credit Spread Forecasting

This project implements an advanced system for credit spread prediction using machine learning techniques and market regime analysis. The system combines data from various financial sources and utilizes models such as Random Forest and XGBoost with early stopping to optimize predictions.

## Key Features

- **Multi-source Analysis**:
  - Integration of data from FRED, Yahoo Finance, and TED Rate
  - Economic and monetary policy indicators
  - Automatic time series synchronization
  - Financial data discrepancy management

- **Causal Feature Engineering**:
  - Optimized temporal lag generation
  - Adaptive window moving averages
  - Advanced technical indicators (RSI, MACD, Bollinger)
  - Market regime features

- **Advanced Models**:
  - Random Forest with custom early stopping
  - XGBoost with Bayesian optimization
  - Market regime analysis with HMM
  - Weighted voting ensemble learning

- **Robust Preprocessing**:
  - Automatic skewness handling
  - Adaptive data standardization
  - Robust outlier treatment
  - Stratified temporal validation

## Requirements

```python
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=0.24.2
xgboost>=1.4.2
hmmlearn>=0.2.7
factor_analyzer>=0.4.0
pandas_datareader>=0.10.0
yfinance>=0.1.70
statsmodels>=0.13.0
seaborn>=0.11.2
matplotlib>=3.4.3
scikit-optimize>=0.9.0
```

## Project Structure

### Core Components

- `CommonConfig`:
  - Date and time series configuration management
  - Global paths and parameters definition
  - Configuration validation

- `CommonDataLoader`:
  - Multi-source data loading management
  - Time series synchronization
  - Intelligent data caching

- `EarlyStoppingRandomForest`:
  - Custom Random Forest implementation
  - Dynamic performance monitoring
  - Automatic tree number optimization

- `ModelTuner`:
  - RF and XGBoost hyperparameter optimization
  - Temporal cross-validation
  - Custom metrics

- `MarketRegimeAnalyzer`:
  - HMM regime analysis
  - Transition matrix calculation
  - State number optimization

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/credit-spread-prediction.git
   cd credit-spread-prediction
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   .\venv\Scripts\activate  # Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Basic Configuration
```python
from config import CommonConfig
from data_loader import CommonDataLoader

# Initialize configuration
config = CommonConfig(
    start_date="2010-01-01",
    end_date="2023-12-31",
    prediction_horizon=30
)

# Load data
loader = CommonDataLoader(config)
data = loader.load_all_sources()
```

### Preprocessing and Feature Engineering
```python
from preprocessing import preprocess_data
from feature_engineering import create_features

# Basic preprocessing
df_processed = preprocess_data(
    data,
    handle_missing=True,
    remove_outliers=True
)

# Feature engineering
df_features = create_features(
    df_processed,
    lag_window=30,
    ma_windows=[7, 14, 30]
)
```

### Training and Evaluation
```python
from models import EarlyStoppingRandomForest, XGBoostOptimized

# Training Random Forest
rf_model = EarlyStoppingRandomForest(
    n_estimators=1000,
    early_stopping_rounds=50
)
rf_model.fit(X_train, y_train, eval_set=(X_val, y_val))

# Training XGBoost
xgb_model = XGBoostOptimized(
    max_depth=6,
    learning_rate=0.01
)
xgb_model.fit(X_train, y_train)
```

## Advanced Features

### Random Forest with Early Stopping
- Continuous performance monitoring
- Automatic tree number optimization
- Dedicated validation set
- Dynamic overfitting management

### XGBoost with Bayesian Optimization
- Optimal hyperparameter search
- Early stopping on validation set
- Automatic overfitting management
- Custom metrics

### Market Regime Analysis
- Automatic regime identification
- Transition matrix calculation
- State number optimization
- Regime-specific predictions

## Contributing

You are welcome to contribute to the project. To do so:
1. Fork the repository
2. Create a branch for your changes
3. Submit a pull request

## License

This project is distributed under the MIT License.

## Citations

If you use this project in your research, please cite:

```bibtex
@software{credit_spread_prediction,
  author = {Author Name},
  title = {Credit Spread Prediction Project},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/yourusername/credit-spread-prediction}
}
```
