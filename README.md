# Monte Carlo Stock Price Simulation

A simple Python script that uses a Monte Carlo simulation to model possible future
price paths for a stock and estimate its market risk.

## What it does

1. Downloads historical daily closing prices for a stock using [yfinance](https://pypi.org/project/yfinance/).
2. Calculates the daily returns, average return (drift), and volatility (risk).
3. Runs many simulated price paths over a future time horizon using Geometric
   Brownian Motion (GBM).
4. Estimates the 95% Value at Risk (VaR): the worst-case price in the bottom 5% of outcomes.
5. Plots all simulated price paths with the VaR threshold marked.

## Requirements

Install the dependencies:

```bash
pip install -r requirements.txt
```

- numpy
- pandas
- matplotlib
- yfinance

## Usage

```bash
python monte_carlo.py
```

The script prints the current price, the 5% worst-case price, and the Value at Risk
per share, then displays a chart of the simulated paths.

## Note: variables are hardcoded

All of the key parameters are hardcoded directly in `monte_carlo.py` rather than
passed in as arguments or read from config. To simulate a different stock or scenario,
edit these values in the script:

- `ticker` — the stock symbol (default: `'AAPL'`)
- `start` / `end` dates in `yf.download(...)` — the historical window used to
  estimate drift and volatility (default: `2022-01-01` to `2024-01-01`)
- `simulations` — number of simulated price paths (default: `1000`)
- `days` — the future time horizon in trading days (default: `30`)

## Disclaimer

This is an educational project. It is not financial advice and should not be used
to make real investment decisions.
