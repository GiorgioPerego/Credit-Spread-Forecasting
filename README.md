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
