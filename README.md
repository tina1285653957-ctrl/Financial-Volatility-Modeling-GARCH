<h1 style="line-height:1.2;text-align:center;">
Financial Volatility Modeling — GARCH Toolkit<br>
金融波动率建模 — GARCH 工具箱
</h1>

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

<blockquote style="text-align:center; line-height:1.5;">
<b>A reusable, production-ready GARCH volatility modeling toolkit for financial time series analysis</b><br>
<i>By Lyra | Designed for practitioners, researchers, and finance students</i><br><br>
<b>一个可复用、可用于实际场景的 GARCH 波动率建模工具，用于金融时间序列分析</b><br>
<i>作者：Lyra ｜ 供从业者、研究人员和金融学生参考</i>
</blockquote>



##  Overview 简介

This toolkit provides a **comprehensive, modular framework** for modeling and forecasting financial volatility using **GARCH (Generalized Autoregressive Conditional Heteroskedasticity)** models. Built with flexibility and reusability in mind, it supports multiple data sources and offers complete end-to-end volatility analysis workflow.

大家好，我是 Lyra！这是我整理的一个用于金融波动率建模的工具箱，主要使用 GARCH 模型。如果你对量化投资、风险管理或者市场波动分析感兴趣，这个项目或许能帮到你！

### Why GARCH? 为什么...选择GARCH呢？

GARCH models are the industry standard for financial volatility modeling because they:
- **Capture volatility clustering** — periods of high volatility tend to follow high volatility
- **Model persistence** — understand how long volatility shocks last in the market
- **Enable risk management** — provide time-varying volatility estimates for VaR and portfolio optimization
- **Support derivatives pricing** — essential for options and other volatility-dependent instruments

GARCH 模型是金融领域里常用的波动率建模方法，它可以：
- **捕捉波动率聚集现象** — 市场波动大的时候往往会持续一段时间
- **衡量波动的持续性** — 看看一次冲击会对市场产生多久的影响
- **辅助风险管理** — 为风险价值和投资组合优化提供时变的波动率估计
- **支持衍生品定价** — 对期权等依赖波动率的产品特别有用

### Key Applications 这个工具可以用在......?

- **Risk Management**: Value-at-Risk (VaR) calculation and portfolio risk assessment
- **Trading Strategies**: Volatility-based position sizing and risk-adjusted returns
- **Derivatives Pricing**: Volatility forecasts for options and structured products
- **Market Analysis**: Understanding volatility regimes and market stress periods

- **风险管理**: 计算风险价值（VaR）和评估投资组合风险
- **交易策略**: 基于波动率调整头寸大小，优化风险调整后收益
- **衍生品定价**: 为期权等产品提供波动率预测
- **市场分析**: 理解不同的波动率区间和市场压力时期
---

##  Features

###  Core Capabilities 核心能力

- **Flexible Data Sources 灵活的数据来源 由你选择**
  -  **yfinance** — No API token required (default)
  -  **🇨🇳 TuShare** — Chinese market data (requires token)
  -  **CSV Files** — Custom data import

- **灵活的数据来源 由你选择**
  -  **yfinance** — 不需要 API 密钥（默认选项）
  -  **🇨🇳 TuShare** — 获取中国股市数据（需要配置 token，有时有积分限制）
  -  **CSV 文件** — 支持导入自定义数据

- **Comprehensive Model Specifications**
  -  **Mean Models** — `Zero`, `Constant`, `AR(1)`
  -  **Volatility Models** — `ARCH`, `GARCH`
  -  **Distributions** — `Normal`, `Student's t`
  -  **Default** — `GARCH(1,1)` with constant mean

- **包含了多种模型**
-  **均值模型** — 零均值、常数均值、AR(1)
-  **波动率模型** — ARCH、GARCH
-  **分布假设** — 正态分布、学生t分布
-  **默认设置** — GARCH(1,1) 配合常数均值

- **Complete Analysis Pipeline**
  -  Data loading and preprocessing
  -  Log returns calculation
  -  GARCH model estimation
  -  Conditional volatility extraction
  -  Multi-period volatility forecasting
  -  Model diagnostics and residual analysis

- **完整的分析流程**
-  数据加载和预处理
-  计算对数收益率
-  估计 GARCH 模型
-  提取条件波动率
-  多期波动率预测
-  模型诊断和残差分析
  

- **Professional Outputs**
  -  High-resolution visualizations
  -  Annualized conditional volatility plots
  -  Standardized residuals analysis
  -  CSV exports for forecasts and model summaries

- **专业的输出结果**
-  高清可视化图表
-  年化条件波动率图
-  标准化残差分析
-  预测结果和模型摘要的 CSV 导出

###  User-Friendly Design

- **Single-section parameter configuration** — Change parameters in one place, run the entire workflow
- **Bilingual documentation** — Chinese and English comments for accessibility
- **Automatic folder creation** — Output directories created automatically
- **Error handling** — Clear error messages for data source issues

###  更友好的设计

- **参数集中配置** — 在一个地方修改参数，就能运行整个流程
- **中英双语注释** — 方便中文用户理解代码
- **自动创建文件夹** — 输出目录会自动生成
- **错误处理** — 清晰的数据源错误提示

---


##  Quick Start 
##  快速开始 —— 只需

### Example: Analyzing Apple Stock Volatility
### 示例：分析苹果股票波动率
```python
SYMBOL = "AAPL"           # 股票代码
START = "2020-01-01"      # 开始日期
END = "2024-01-01"        # 结束日期
DATA_SOURCE = "yfinance"  # 数据源
MEAN_MODEL = "Constant"   # 均值模型
VOL_MODEL = "GARCH"       # 波动率模型
P, Q = 1, 1               # GARCH 阶数
DIST = "normal"           # 分布假设
FORECAST_STEPS = 30       # 预测步长
```

Run the notebook to get:
- Apple's historical conditional volatility
- 30-day ahead volatility forecast
- Model diagnostics and residual analysis

运行后你将得到：
- 苹果股票的历史条件波动率
- 未来30天的波动率预测
- 模型诊断和残差分析结果

---

##  Outputs 输出内容

All outputs are automatically saved to:
所有结果会自动保存到

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

##  Project Structure 项目结构

```
Financial-Volatility-Modeling-GARCH/
├── GARCH_toolkit_yf.ipynb    # Main analysis notebook 主分析文件
├── README.md                  # Project documentation (this file) 项目说明（就是这个文件）
├── env.example               # Template for environment variables 环境变量模板
├── .gitignore                # Git ignore rules Git的忽略规则
├── .gitattributes            # Git attributes Git的属性设置
├── figures/                  # Auto-generated plots (created on run) 自动生成的图表（运行后创建）
│   ├── garch_conditional_vol_annualized.png
│   ├── standardized_residuals.png
│   └── standardized_resid_hist.png
└── outputs/                  # Auto-generated CSVs (created on run) 自动生成的数据文件（运行后创建）
    ├── forecast_annualized_vol.csv
    └── garch_summary.csv
```

---


##  Usage Examples 使用示例

### Example 1: S&P 500 Volatility Analysis 分析标普500波动率

```python
# Configure for S&P 500 配置标普500分析
SYMBOL = "^GSPC"      # 标普500指数
START = "2015-01-01"
END = "2024-01-01"
DATA_SOURCE = "yfinance"
MEAN_MODEL = "Constant"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "t"  # Student's t for fat tails  使用学生t分布处理厚尾
FORECAST_STEPS = 20
```

### Example 2: Chinese Stock Market (TuShare) 中国股市分析（TuShare）

```python
# Configure for Shanghai Stock Exchange 配置A股分析
SYMBOL = "600036.SH"  # China Merchants Bank
START = "2018-01-01"
END = "2024-01-01"
DATA_SOURCE = "tushare"  # Requires TUSHARE_TOKEN in .env 需要在 .env 中设置 TUSHARE_TOKEN
MEAN_MODEL = "AR(1)"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "normal"
FORECAST_STEPS = 30
```

### Example 3: Custom CSV Data 使用自定义CSV数据

```python
# Prepare your CSV with columns: datetime, close
# Example format:
# datetime,close
# 2020-01-01,100.5
# 2020-01-02,101.2
# ...

CSV_PATH = "your_data.csv"  # 你的数据文件路径
DATA_SOURCE = "csv"
MEAN_MODEL = "Constant"
VOL_MODEL = "GARCH"
P, Q = 1, 1
DIST = "normal"
FORECAST_STEPS = 20
```
---

## 🐛 Troubleshooting 常见问题

### Common Issues 可能出现的问题...不要沮丧！！！

**Issue**: `ImportError: No module named 'yfinance'`  
**Solution**: Install missing package: `pip install yfinance`

**Issue**: `ValueError: yfinance returned no data`  
**Solution**: Check symbol format (e.g., use `^GSPC` for S&P 500, `.SS` for Shanghai)

**Issue**: `TuShare Token Error`  
**Solution**: Ensure `.env` file exists with correct `TUSHARE_TOKEN=your_token`

**Issue**: `CSV must contain datetime/close columns`  
**Solution**: Ensure your CSV has columns named `datetime` (or `date`, `Date`) and `close` (or `Close`, `Adj Close`)

### Getting Help  需要帮助？没有问题！

- Open an [Issue](https://github.com/tina1285653957-ctrl/Financial-Volatility-Modeling-GARCH/issues)
- Check existing issues for similar problems
- Provide error messages and your configuration when reporting bugs

---

## 👤 Author  关于我

**Lyra**  
GitHub: [@tina1285653957-ctrl](https://github.com/tina1285653957-ctrl)

---

##  Personal Note 个人心得

GARCH modeling is powerful for understanding **volatility clustering and risk regimes** in financial markets. This toolkit prioritizes **reusability** and **standardization**: unified data interfaces, fixed modeling steps, and consistent outputs. In real investment research, I adjust distributions and model orders based on residual diagnostics to better match asset characteristics. The goal is to make volatility analysis accessible while maintaining professional standards.

GARCH 模型在理解金融市场中的波动率聚集和风险区间方面真的很强大。我做这个工具箱时特别注重可复用性和标准化：统一的数据接口、固定的建模步骤、一致的输出格式。在实际的投资研究中，我通常会根据残差诊断来调整分布假设和模型阶数，以更好地匹配资产特性。希望这个工具能让波动率分析变得更简单，同时保持专业水准。

---

**⭐ If you find this toolkit useful, please consider giving it a star on GitHub! ⭐**
**⭐ 如果你觉得这个工具有用，请在 GitHub 上给它一个 star 支持一下！⭐**

---

*Last Updated: 2025/10/26*
