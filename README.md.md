# 📉 Financial Volatility Modeling — GARCH Toolkit  
**by Lyra**

A reusable GARCH toolkit with analyst-style notes. Default data source: **yfinance** (no token). Optional **TuShare** (token) and **CSV**.

## Quick Start
1. Open `GARCH_toolkit_yf.ipynb`
2. Edit **0. Parameters** (symbol/date/source/spec)
3. Run All. Figures → `figures/`, CSVs → `outputs/`

## Install
```
pip install numpy pandas matplotlib arch yfinance tushare
```

## Outputs
- `figures/garch_conditional_vol_annualized.png`
- `figures/standardized_residuals.png`
- `figures/standardized_resid_hist.png`
- `outputs/forecast_annualized_vol.csv`
- `outputs/garch_summary.csv`
