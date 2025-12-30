# 📈 Portfolio Optimization for Cross-Asset Allocation

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.21%2B-013243.svg)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-150458.svg)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Winner Project - Arbitrage Arena 2025 | IISc Bangalore**

[📘 View Notebook](Portfolio_Optimization_ArbitrageArena.ipynb) • [📊 Presentation](Portfolio_Optimization_Presentation.pptx) • [🏆 Competition](https://pravega.in)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Key Features](#-key-features)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Installation](#-installation)
- [Usage](#-usage)
- [Results](#-results)
- [Project Structure](#-project-structure)
- [Technologies Used](#-technologies-used)
- [Performance Metrics](#-performance-metrics)
- [Visualizations](#-visualizations)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)
- [Acknowledgments](#-acknowledgments)

---

## 🎯 Overview

This project implements a **professional-grade portfolio optimization system** using **Mean-Variance Optimization (Markowitz Portfolio Theory)** to build an optimal multi-asset portfolio. The system analyzes 12 assets across 4 asset classes over a 6.3-year period (Jan 2018 - May 2024) to maximize risk-adjusted returns while minimizing drawdowns.

### 🏆 Competition Achievement
- **Event:** Arbitrage Arena 2025 - Pravega, IISc Bangalore
- **Challenge:** Cross-Asset Portfolio Optimization
- **Result:** Achieved **Sharpe Ratio of 1.458** with **389% total return**

---

## 💡 Problem Statement

**Challenge:** Build a diversified systematic portfolio across equities, indices, commodities, and cryptocurrencies with:
- ✅ High Sharpe ratio (risk-adjusted returns)
- ✅ Low maximum drawdowns
- ✅ Robust performance across market cycles
- ✅ Systematic rebalancing strategy

**Objective:** Develop and backtest a portfolio optimization model that outperforms equal-weight and single-asset strategies on a risk-adjusted basis.

---

## ✨ Key Features

### Core Functionality
- 📊 **Multi-Asset Analysis:** 12 assets across Tech Stocks, Index, Commodities, and Cryptocurrencies
- 🔬 **Mean-Variance Optimization:** Implements Markowitz Portfolio Theory
- 📈 **Efficient Frontier Generation:** 50 optimal portfolios across risk-return spectrum
- 🎯 **Dual Optimization Strategies:**
  - Maximum Sharpe Ratio Portfolio (recommended)
  - Minimum Variance Portfolio (defensive)
- 🔄 **Comprehensive Backtesting:** 6.3 years of historical validation
- 📉 **Advanced Risk Metrics:** Sharpe, Sortino, Calmar, VaR, Drawdown Analysis
- 📊 **Professional Visualizations:** 15+ charts including equity curves, heatmaps, efficient frontier

### Technical Features
- ✅ Data cleaning and preprocessing pipeline
- ✅ Missing value handling and date alignment
- ✅ Rolling window analysis (volatility, Sharpe ratio)
- ✅ Correlation matrix analysis
- ✅ Monthly returns heatmap
- ✅ Transaction-free backtesting framework

---

## 📁 Dataset

### Asset Composition

| Asset Class | Assets | Count |
|-------------|--------|-------|
| **Tech Stocks** | Apple, Amazon, Microsoft, Tesla, NVIDIA, Meta | 6 |
| **Index** | NASDAQ-100 | 1 |
| **Commodities** | Gold, Silver, Crude Oil (WTI) | 3 |
| **Cryptocurrencies** | Bitcoin (BTC), Ethereum (ETH) | 2 |
| **Total** | | **12** |

### Dataset Details
- **Time Period:** January 18, 2018 - May 10, 2024
- **Duration:** 6.31 years
- **Trading Days:** 1,588
- **Data Frequency:** Daily OHLCV (Open, High, Low, Close, Volume)
- **Data Quality:** ✅ No missing values after preprocessing
- **Source:** Historical market data from exchanges and financial APIs

### Data Format
```
Columns: Date, Price, Open, High, Low, Volume, Change %
Format: CSV files (12 separate files)
Size: ~3.5 MB total
```

---

## 🔬 Methodology

### 1. Data Preprocessing
```
Pipeline Steps:
1. Load 12 CSV files
2. Clean price columns (remove commas, convert to float)
3. Handle missing values (forward/backward fill)
4. Align dates to common range (Jan 2018 - May 2024)
5. Create unified price matrix (1,588 × 12)
```

### 2. Exploratory Data Analysis
- Normalized price trends
- Return distribution analysis
- Correlation matrix computation
- Risk-return profile scatter plots
- Rolling volatility analysis

### 3. Portfolio Optimization

**Mean-Variance Optimization Framework:**

**Portfolio Return:**
```
R_p = Σ(w_i × R_i)
```

**Portfolio Variance:**
```
σ²_p = w^T × Σ × w
```

**Sharpe Ratio (Objective Function):**
```
SR = R_p / σ_p
```

**Constraints:**
- Fully invested: Σw_i = 1
- No short selling: 0 ≤ w_i ≤ 1
- No leverage constraint

**Optimization Algorithm:**
- Method: Sequential Least Squares Programming (SLSQP)
- Library: `scipy.optimize.minimize`
- Convergence: ✓ Successfully converged for both strategies

### 4. Backtesting Framework
```
Backtesting Process:
1. Apply optimized weights to historical returns
2. Calculate daily portfolio value
3. Compute cumulative returns
4. Track drawdowns (peak-to-trough)
5. Calculate comprehensive performance metrics
6. Compare against benchmarks
```

---

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or Google Colab
- 8GB RAM recommended

### Setup Instructions

**1. Clone the Repository**
```bash
git clone https://github.com/amanraj74/portfolio-optimization.git
cd portfolio-optimization
```

**2. Create Virtual Environment (Recommended)**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

**3. Install Dependencies**
```bash
pip install -r requirements.txt
```

**4. Launch Jupyter Notebook**
```bash
jupyter notebook Portfolio_Optimization_ArbitrageArena.ipynb
```

### Requirements.txt
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scipy>=1.7.0
jupyter>=1.0.0
```

---

## 💻 Usage

### Quick Start

**1. Open the Jupyter Notebook**
```bash
jupyter notebook Portfolio_Optimization_ArbitrageArena.ipynb
```

**2. Run All Cells**
- Click `Kernel` → `Restart & Run All`
- Or run cells sequentially (Shift + Enter)

**3. Review Results**
- Scroll through visualizations
- Check final performance metrics
- Analyze portfolio allocations

### Customize Parameters

**Modify Optimization Constraints:**
```python
# Example: Add maximum allocation constraint (no asset > 30%)
bounds = tuple((0, 0.3) for _ in range(num_assets))
```

**Change Risk-Free Rate:**
```python
# Add risk-free rate to Sharpe calculation
risk_free_rate = 0.03  # 3% annual
sharpe_ratio = (portfolio_return - risk_free_rate) / portfolio_volatility
```

**Adjust Backtesting Period:**
```python
# Use specific date range
start_date = '2020-01-01'
end_date = '2024-05-10'
filtered_data = price_data[start_date:end_date]
```

---

## 📊 Results

### 🏆 Maximum Sharpe Ratio Portfolio (Recommended)

| Metric | Value |
|--------|-------|
| **Expected Annual Return** | 28.63% |
| **Annualized Volatility** | 19.64% |
| **Sharpe Ratio** | **1.458** ⭐ |
| **Sortino Ratio** | 2.003 |
| **Maximum Drawdown** | -32.37% |
| **Calmar Ratio** | 0.884 |
| **Win Rate** | 55.60% |
| **Total Return (6.3 yrs)** | **388.77%** |
| **Final Portfolio Value** | **$494,172** (from $100,000) |

### 📈 Optimal Asset Allocation

```
Gold:  54.1% ← Stability & diversification anchor
NVDA:  18.6% ← Growth component (AI boom)
MSFT:  10.7% ← Cloud computing exposure
BTC:    8.3% ← Crypto upside, controlled allocation
TSLA:   6.4% ← EV revolution exposure
AAPL:   1.2% ← Additional tech diversification
OIL:    0.7% ← Commodity exposure
```

### 🎯 Key Achievements

✅ **Superior Risk-Adjusted Returns:** Sharpe ratio of 1.458 vs 1.178 (equal-weight benchmark)  
✅ **Controlled Drawdowns:** -32.37% vs -42.26% (equal-weight)  
✅ **Consistent Performance:** 66.2% winning months  
✅ **Recovery Ability:** Full recovery from COVID-19 crash and 2022 correction  
✅ **Diversification Benefit:** Reduced volatility by 27% vs equal-weight strategy

### 📊 Performance Comparison

| Strategy | Return | Volatility | Sharpe | Max DD | Final Value |
|----------|--------|------------|--------|--------|-------------|
| **Maximum Sharpe** | 28.63% | 19.64% | **1.458** | -32.37% | $494,172 |
| Minimum Variance | 12.14% | 13.26% | 0.915 | -19.40% | $206,686 |
| Equal Weight | 32.24% | 27.36% | 1.178 | -42.26% | $585,564 |

---

## 📂 Project Structure

```
portfolio-optimization/
│
├── README.md                                    # Project documentation
├── requirements.txt                             # Python dependencies
├── LICENSE                                      # MIT License
│
├── Portfolio_Optimization_ArbitrageArena.ipynb  # Main Jupyter Notebook
├── Portfolio_Optimization_Presentation.pptx     # Competition Presentation
│
├── data/                                        # Dataset folder
│   ├── Apple-Stock-Price-History.csv
│   ├── Amazon.com-Stock-Price-History.csv
│   ├── Microsoft-Stock-Price-History.csv
│   ├── Tesla-Stock-Price-History.csv
│   ├── NVIDIA-Stock-Price-History.csv
│   ├── Meta-Platforms-Stock-Price-History.csv
│   ├── Nasdaq-100-Historical-Data.csv
│   ├── Gold-Futures-Historical-Data.csv
│   ├── Silver-Futures-Historical-Data.csv
│   ├── Crude-Oil-WTI-Futures-Historical-Data.csv
│   ├── BTC_USD-Bitfinex-Historical-Data.csv
│   └── ETH_USD-Binance-Historical-Data.csv
│
├── images/                                      # Visualization outputs
│   ├── normalized_prices.png
│   ├── correlation_matrix.png
│   ├── efficient_frontier.png
│   ├── equity_curves.png
│   ├── drawdown_analysis.png
│   ├── portfolio_allocations.png
│   └── monthly_returns_heatmap.png
│
└── docs/                                        # Additional documentation
    ├── methodology.md
    ├── results_analysis.md
    └── future_enhancements.md
```

---

## 🛠️ Technologies Used

### Core Libraries
- **Python 3.8+** - Primary programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing and array operations
- **SciPy** - Optimization algorithms (SLSQP)
- **Matplotlib** - Data visualization and plotting
- **Seaborn** - Statistical data visualization

### Development Tools
- **Jupyter Notebook** - Interactive development environment
- **Google Colab** - Cloud-based notebook execution
- **Git** - Version control
- **GitHub** - Code repository and collaboration

### Key Algorithms
- **Mean-Variance Optimization** (Markowitz, 1952)
- **Sequential Least Squares Programming** (SLSQP)
- **Efficient Frontier Construction**
- **Rolling Window Analysis**

---

## 📈 Performance Metrics

### Risk Metrics
```
Volatility (Annualized):     19.64%
Maximum Drawdown:            -32.37%
Downside Deviation:          14.30%
Value at Risk (95%):         -1.80%
Conditional VaR (95%):       -3.45%
```

### Return Metrics
```
Total Return:                388.77%
Annualized Return:           28.63%
Compound Annual Growth:      27.89%
Average Monthly Return:      2.39%
Best Day Return:             8.90%
Worst Day Return:            -9.04%
```

### Risk-Adjusted Metrics
```
Sharpe Ratio:                1.458
Sortino Ratio:               2.003
Calmar Ratio:                0.884
Information Ratio:           0.625
Omega Ratio:                 1.328
```

### Consistency Metrics
```
Win Rate (Daily):            55.60%
Win Rate (Monthly):          66.23%
Average Win:                 0.90%
Average Loss:                -0.88%
Win/Loss Ratio:              1.02
```

---

## 🎨 Visualizations

### Available Charts

1. **Normalized Price Trends** - All 12 assets indexed to 100
2. **Return Distributions** - Histograms for each asset
3. **Correlation Heatmap** - Asset correlation matrix
4. **Risk-Return Scatter Plot** - Individual asset positioning
5. **Efficient Frontier** - 50 optimal portfolios
6. **Portfolio Allocations** - Pie charts for both strategies
7. **Equity Curves** - Backtested portfolio performance
8. **Drawdown Analysis** - Peak-to-trough decline tracking
9. **Rolling Sharpe Ratio** - 1-year rolling window
10. **Monthly Returns Heatmap** - Year-over-year performance

### Sample Visualization

```python
# Generate Efficient Frontier
plt.figure(figsize=(14, 9))
plt.plot(ef_volatility, ef_returns, linewidth=4, label='Efficient Frontier')
plt.scatter(max_sharpe_vol*100, max_sharpe_return*100, 
            marker='*', s=800, c='red', label='Maximum Sharpe')
plt.xlabel('Volatility (%)')
plt.ylabel('Return (%)')
plt.title('Efficient Frontier with Optimal Portfolios')
plt.legend()
plt.show()
```

---

## 🚀 Future Enhancements

### Planned Features

#### Short-Term (v2.0)
- [ ] **Transaction Costs:** Include realistic trading costs (0.1-0.5%)
- [ ] **Dynamic Rebalancing:** Monthly/quarterly portfolio rebalancing
- [ ] **Tax Optimization:** Capital gains tax considerations
- [ ] **Regime Detection:** Bull/bear market identification
- [ ] **Walk-Forward Analysis:** Out-of-sample testing

#### Medium-Term (v3.0)
- [ ] **Black-Litterman Model:** Incorporate forward-looking views
- [ ] **Risk Parity Strategy:** Alternative allocation approach
- [ ] **Factor Models:** Fama-French multi-factor analysis
- [ ] **Machine Learning Integration:** Return prediction models
- [ ] **Multi-Period Optimization:** Long-term horizon planning

#### Long-Term (v4.0)
- [ ] **Real-Time Data Integration:** Live market data feeds
- [ ] **Automated Trading System:** Execute trades programmatically
- [ ] **Dashboard Application:** Interactive Streamlit/Dash app
- [ ] **API Development:** RESTful API for portfolio optimization
- [ ] **Database Integration:** PostgreSQL for historical data storage

### Research Extensions
- Monte Carlo simulation for confidence intervals
- Stress testing across historical crisis periods
- CVaR (Conditional Value at Risk) optimization
- Multi-objective optimization (return, risk, ESG)
- Cryptocurrency-focused portfolio strategies

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

### How to Contribute

1. **Fork the Repository**
```bash
git fork https://github.com/amanraj74/portfolio-optimization.git
```

2. **Create Feature Branch**
```bash
git checkout -b feature/YourFeatureName
```

3. **Commit Changes**
```bash
git commit -m "Add: Your feature description"
```

4. **Push to Branch**
```bash
git push origin feature/YourFeatureName
```

5. **Open Pull Request**
- Describe your changes
- Reference any related issues
- Include test results

### Contribution Guidelines
- Follow PEP 8 style guide
- Add docstrings to all functions
- Include unit tests for new features
- Update README for significant changes
- Maintain backward compatibility

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### MIT License Summary
```
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, subject to including copyright notice.
```

---

## 👨‍💻 Author

**Aman Jaiswal**

- 🎓 BCA 3rd Year Student
- 📧 Email: [aerraj50@gmail.com](mailto:aerraj50@gmail.com)
- 🐱 GitHub: [@amanraj74](https://github.com/amanraj74)

### Connect With Me
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/amanraj74)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail)](mailto:aerraj50@gmail.com)

---

## 🙏 Acknowledgments

### Competition
- **Arbitrage Arena 2025** - Indian Institute of Science (IISc), Bangalore
- **Pravega XII** - IISc's Science & Technology Festival
- **Organizing Committee** - For hosting this excellent quantitative finance challenge

### Libraries & Tools
- **SciPy Contributors** - For optimization algorithms
- **Pandas Development Team** - For data manipulation tools
- **Matplotlib & Seaborn** - For visualization capabilities
- **Jupyter Project** - For interactive notebook environment

### Inspiration & References
- **Harry Markowitz (1952)** - "Portfolio Selection" - Foundation of Modern Portfolio Theory
- **William Sharpe (1966)** - Sharpe Ratio development
- **Robert Merton (1972)** - Continuous-time portfolio optimization
- **Quantitative Finance Community** - For ongoing research and methodologies

### Learning Resources
- IISc Bangalore Financial Engineering Courses
- MIT OpenCourseWare - Financial Theory
- Coursera - Investment Management Specialization
- QuantConnect & Quantopian Communities

---

## 📚 References

### Academic Papers
1. Markowitz, H. (1952). "Portfolio Selection". *Journal of Finance*, 7(1), 77-91.
2. Sharpe, W. F. (1966). "Mutual Fund Performance". *Journal of Business*, 39(1), 119-138.
3. Black, F., & Litterman, R. (1992). "Global Portfolio Optimization". *Financial Analysts Journal*, 48(5), 28-43.

### Books
1. *Modern Portfolio Theory and Investment Analysis* - Elton, Gruber, Brown, Goetzmann
2. *Quantitative Portfolio Management* - Michael Isichenko
3. *Active Portfolio Management* - Grinold & Kahn

### Online Resources
- [Investopedia - Portfolio Management](https://www.investopedia.com/portfolio-management/)
- [QuantConnect Documentation](https://www.quantconnect.com/docs/)
- [Portfolio Visualizer](https://www.portfoliovisualizer.com/)

---

## 📊 Project Statistics

![GitHub Stars](https://img.shields.io/github/stars/amanraj74/portfolio-optimization?style=social)
![GitHub Forks](https://img.shields.io/github/forks/amanraj74/portfolio-optimization?style=social)
![GitHub Watchers](https://img.shields.io/github/watchers/amanraj74/portfolio-optimization?style=social)

**Project Stats:**
- 📁 Lines of Code: ~2,500
- 📊 Visualizations: 15+
- 📈 Assets Analyzed: 12
- ⏱️ Backtest Period: 6.31 years
- 📉 Trading Days: 1,588
- 🎯 Performance: 389% total return

---

## ⚠️ Disclaimer

This project is for **educational and research purposes only**. 

**Important Notes:**
- ❌ **NOT financial advice** - Do not use for actual investment decisions
- ❌ **Past performance ≠ future results** - Historical returns do not guarantee future performance
- ❌ **No warranties** - Results may vary with different data or time periods
- ✅ **Educational tool** - For learning portfolio optimization techniques
- ✅ **Research purposes** - For academic and competition use

**Risk Warning:** All investments carry risk. Consult with a qualified financial advisor before making investment decisions.

---

## 📞 Support

### Having Issues?

**Check these first:**
1. 📖 Read the [Installation Guide](#-installation)
2. 💬 Search [existing issues](https://github.com/amanraj74/portfolio-optimization/issues)
3. 📚 Review the [Usage Section](#-usage)

**Still need help?**
- 🐛 [Report a Bug](https://github.com/amanraj74/portfolio-optimization/issues/new?template=bug_report.md)
- 💡 [Request a Feature](https://github.com/amanraj74/portfolio-optimization/issues/new?template=feature_request.md)
- 📧 Email: [aerraj50@gmail.com](mailto:aerraj50@gmail.com)

---

<div align="center">

### ⭐ Star this repository if you found it helpful!

**Made with ❤️ by [Aman Jaiswal](https://github.com/amanraj74)**

*Portfolio Optimization Project - Arbitrage Arena 2025*

</div>

---

**Last Updated:** December 30, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete - Competition Submitted
