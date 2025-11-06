# Quantitative Strategy Backtesting Projects

This repository contains two complete quantitative strategy backtests implemented in Python.

1.  **SMA Crossover:** A classic directional, momentum-based strategy.
2.  **Pairs Trading:** A market-neutral, statistical arbitrage strategy.

---

## Project 1: SMA Crossover Strategy (Directional)

This project backtests a Simple Moving Average (SMA) Crossover strategy on `RELIANCE.NS` against a 'Buy-and-Hold' benchmark.

* **Strategy:** Go Long (Buy) when the 50-day SMA crosses above the 200-day SMA. Go Flat (Sell) when it crosses below.
* **Tech Stack:** Python, Pandas, NumPy, yfinance, Matplotlib.
* **Key Skill:** Demonstrates handling time-series data and **preventing look-ahead bias** using `.shift()`.

### Performance Results (2020 - 2023)

| Metric | BENCHMARK (BUY & HOLD) | SMA CROSSOVER STRATEGY |
| :--- | :---: | :---: |
| Total Return | 89.98% | 53.48% |
| Annual Volatility | 31.18% | 22.17% |
| Sharpe Ratio | 0.68 | 0.60 |

### Analysis

The strategy successfully reduced risk, lowering volatility from 31% to 22%. It underperformed in a bull market but demonstrates a clear risk-management profile by moving to cash during downturns.

![SMA Strategy P&L][(graphsma strategy.png)](https://github.com/Adityarajsingh01/Quant_backtest_project/blob/main/graphsma%20strategy.png)

---

## Project 2: Market-Neutral Pairs Trading (Statistical Arbitrage)

This project backtests a market-neutral statistical arbitrage strategy on a pair of co-integrated NIFTY 50 stocks: `HDFCBANK.NS` and `ICICIBANK.NS`.

* **Strategy:**
    1.  Use OLS regression from `statsmodels` to find the hedge ratio.
    2.  Create a mean-reverting "spread" from the pair.
    3.  Calculate the rolling **Z-Score** of the spread.
    4.  Short the spread at +2.0 std dev and Long the spread at -2.0 std dev.
* **Tech Stack:** Python, Pandas, NumPy, yfinance, Matplotlib, **Statsmodels**.
* **Key Skill:** Demonstrates statistical analysis (regression, Z-Score) to build a market-neutral (alpha-generating) strategy.

### Performance Results (2019 - 2023)

| Metric | NIFTY 50 (BENCHMARK) | PAIRS TRADING STRATEGY |
| :--- | :---: | :---: |
| Total Return | 101.36% | 35.19% |
| Sharpe Ratio | 0.85 | 0.70 |
| **Correlation to NIFTY** | **1.0** | **0.22** |

### Analysis

This strategy was a success. The **0.22 correlation** proves it is genuinely market-neutral. It generated a positive return (Sharpe of 0.70) completely independent of the market's direction, making it a true "alpha" strategy.

![Pairs Trading Strategy P&L](pair_trading.png)
