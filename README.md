#  Financial Volatility Modeling — GARCH Toolkit

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

> **A reusable, production-ready GARCH volatility modeling toolkit for financial time series analysis**  
> *By Lyra* | Designed for practitioners, researchers, and finance students

---

##  Overview

This toolkit provides a **comprehensive, modular framework** for modeling and forecasting financial volatility using **GARCH (Generalized Autoregressive Conditional Heteroskedasticity)** models. Built with flexibility and reusability in mind, it supports multiple data sources and offers complete end-to-end volatility analysis workflow.

### Why GARCH?

GARCH models are the industry standard for financial volatility modeling because they:
- **Capture volatility clustering** — periods of high volatility tend to follow high volatility
- **Model persistence** — understand how long volatility shocks last in the market
- **Enable risk management** — provide time-varying volatility estimates for VaR and portfolio optimization
- **Support derivatives pricing** — essential for options and other volatility-dependent instruments

### Key Applications

- **Risk Management**: Value-at-Risk (VaR) calculation and portfolio risk assessment
- **Trading Strategies**: Volatility-based position sizing and risk-adjusted returns
- **Derivatives Pricing**: Volatility forecasts for options and structured products
- **Market Analysis**: Understanding volatility regimes and market stress periods

---

##  Features

###  Core Capabilities

- **Flexible Data Sources**
  -  **yfinance** — No API token required (default)
  - 🇨🇳 **TuShare** — Chinese market data (requires token)
  -  **CSV Files** — Custom data import

- **Comprehensive Model Specifications**
  - Mean Models: `Zero`, `Constant`, `AR(1)`
  - Volatility Models: `ARCH`, `GARCH`
  - Distributions: `Normal`, `Student's t`
  - Default: `GARCH(1,1)` with constant mean

- **Complete Analysis Pipeline**
  -  Data loading and preprocessing
  -  Log returns calculation
  -  GARCH model estimation
  -  Conditional volatility extraction
  -  Multi-period volatility forecasting
  -  Model diagnostics and residual analysis

- **Professional Outputs**
  -  High-resolution visualizations
  -  Annualized conditional volatility plots
  -  Standardized residuals analysis
  -  CSV exports for forecasts and model summaries

###  User-Friendly Design

- **Single-section parameter configuration** — Change parameters in one place, run the entire workflow
- **Bilingual documentation** — Chinese and English comments for accessibility
- **Automatic folder creation** — Output directories created automatically
- **Error handling** — Clear error messages for data source issues

---


##  Quick Start

### Example: Analyzing Apple Stock Volatility

```python
SYMBOL = "AAPL"
START = "2020-01-01"
END = "2024-01-01"
DATA_SOURCE = "yfinance"
MEAN_MODEL = "Constant"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "normal"
FORECAST_STEPS = 30
```

Run the notebook to get:
- Apple's historical conditional volatility
- 30-day ahead volatility forecast
- Model diagnostics and residual analysis

---

##  Outputs

All outputs are automatically saved to:

### 📁 `figures/` Directory

| File | Description |
|------|-------------|
| `garch_conditional_vol_annualized.png` | Time series plot of annualized conditional volatility |
| `standardized_residuals.png` | Standardized residuals over time |
| `standardized_resid_hist.png` | Distribution histogram of standardized residuals |

### 📁 `outputs/` Directory

| File | Description |
|------|-------------|
| `forecast_annualized_vol.csv` | Multi-period volatility forecasts (annualized) |
| `garch_summary.csv` | Model parameters, specifications, and key statistics |

---

##  Project Structure

```
Financial-Volatility-Modeling-GARCH/
├── GARCH_toolkit_yf.ipynb    # Main analysis notebook
├── README.md                  # Project documentation (this file)
├── env.example               # Template for environment variables
├── .gitignore                # Git ignore rules
├── .gitattributes            # Git attributes
├── figures/                  # Auto-generated plots (created on run)
│   ├── garch_conditional_vol_annualized.png
│   ├── standardized_residuals.png
│   └── standardized_resid_hist.png
└── outputs/                  # Auto-generated CSVs (created on run)
    ├── forecast_annualized_vol.csv
    └── garch_summary.csv
```

---


##  Usage Examples

### Example 1: S&P 500 Volatility Analysis

```python
# Configure for S&P 500
SYMBOL = "^GSPC"
START = "2015-01-01"
END = "2024-01-01"
DATA_SOURCE = "yfinance"
MEAN_MODEL = "Constant"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "t"  # Student's t for fat tails
FORECAST_STEPS = 20
```

### Example 2: Chinese Stock Market (TuShare)

```python
# Configure for Shanghai Stock Exchange
SYMBOL = "600036.SH"  # China Merchants Bank
START = "2018-01-01"
END = "2024-01-01"
DATA_SOURCE = "tushare"  # Requires TUSHARE_TOKEN in .env
MEAN_MODEL = "AR(1)"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "normal"
FORECAST_STEPS = 30
```

### Example 3: Custom CSV Data

```python
# Prepare your CSV with columns: datetime, close
# Example format:
# datetime,close
# 2020-01-01,100.5
# 2020-01-02,101.2
# ...

CSV_PATH = "your_data.csv"
DATA_SOURCE = "csv"
MEAN_MODEL = "Constant"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "normal"
FORECAST_STEPS = 20
```
---

## 🐛 Troubleshooting

### Common Issues

**Issue**: `ImportError: No module named 'yfinance'`  
**Solution**: Install missing package: `pip install yfinance`

**Issue**: `ValueError: yfinance returned no data`  
**Solution**: Check symbol format (e.g., use `^GSPC` for S&P 500, `.SS` for Shanghai)

**Issue**: `TuShare Token Error`  
**Solution**: Ensure `.env` file exists with correct `TUSHARE_TOKEN=your_token`

**Issue**: `CSV must contain datetime/close columns`  
**Solution**: Ensure your CSV has columns named `datetime` (or `date`, `Date`) and `close` (or `Close`, `Adj Close`)

### Getting Help

- Open an [Issue](https://github.com/tina1285653957-ctrl/Financial-Volatility-Modeling-GARCH/issues)
- Check existing issues for similar problems
- Provide error messages and your configuration when reporting bugs

---

## 👤 Author

**Lyra**  
GitHub: [@tina1285653957-ctrl](https://github.com/tina1285653957-ctrl)

---

##  Personal Note

GARCH modeling is powerful for understanding **volatility clustering and risk regimes** in financial markets. This toolkit prioritizes **reusability** and **standardization**: unified data interfaces, fixed modeling steps, and consistent outputs. In real investment research, I adjust distributions and model orders based on residual diagnostics to better match asset characteristics. The goal is to make volatility analysis accessible while maintaining professional standards.

---

**⭐ If you find this toolkit useful, please consider giving it a star on GitHub! ⭐**

---

*Last Updated: 2025/10/26*
