# SMA Crossover Strategy Backtest

This is a Python-based backtesting engine to analyze the performance of a Simple Moving Average (SMA) Crossover strategy on RELIANCE.NS.

- **Strategy:** Go Long (Buy) when the 50-day SMA crosses above the 200-day SMA. Go Flat (Sell) when it crosses below.
- **Benchmark:** Simple "Buy and Hold" strategy.
- **Tech Stack:** Python, Pandas, NumPy, yfinance, Matplotlib

---

## Backtest Results (Jan 2020 - Dec 2023)

| Metric | BENCHMARK (BUY & HOLD) | SMA CROSSOVER STRATEGY |
| :--- | :---: | :---: |
| Total Return | 89.98% | 53.48% |
| Annual Volatility | 31.18% | 22.17% |
| Sharpe Ratio | 0.68 | 0.60 |

### Performance Plot

![Strategy P&L](backtest_sma.ipynb)

### Key Analysis
The strategy successfully reduced risk (volatility) by almost 30% compared to the benchmark, moving to cash during significant downturns.# Quant_backtest_project
