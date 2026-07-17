# 📈 Simple Backtesting Strategy

A Python-based backtesting tool that evaluates a **Simple Moving Average (SMA) crossover strategy** on historical stock data. It downloads one year of price data, generates long/short signals, and reports key performance metrics alongside visualizations.

> **Note:** This project was built as a recruitment task submission for **Quant Club @ BITS Pilani**.

## Strategy Overview

The strategy uses a **10-day Simple Moving Average (SMA)** to make daily trading decisions:

| Condition | Signal |
|---|---|
| Close price ≥ 10-day SMA | **Long** (+1) |
| Close price < 10-day SMA | **Short** (−1) |

At each trading day, the position is determined by comparing the current closing price against the average of the previous *N* closing prices. The strategy is fully invested at all times — either long or short.

## Performance Metrics

The script computes and prints the following metrics:

- **Total Return** — Cumulative profit/loss over the backtesting period.
- **Sharpe Ratio** — Risk-adjusted return (daily, non-annualized), calculated as the mean daily return divided by the standard deviation of daily returns.
- **Max Drawdown** — Largest peak-to-trough decline in cumulative PnL, expressed as a fraction.

## Output Charts

Three charts are saved to the `images/` directory:

| Chart | File | Description |
|---|---|---|
| Cumulative PnL | `images/cumulative_pnl.png` | Running total profit/loss over time |
| Daily Position | `images/daily_position.png` | Long (+1) or short (−1) signal per day |
| Daily PnL | `images/daily_pnl.png` | Profit/loss for each individual trading day |

## Prerequisites

- Python 3.8+

## Installation

```bash
git clone https://github.com/brokenCart/simple-backtesting-strategy.git
cd simple-backtesting-strategy
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

### Dependencies

| Package | Version | Purpose |
|---|---|---|
| [yfinance](https://pypi.org/project/yfinance/) | 1.2.0 | Download historical stock data from Yahoo Finance |
| [matplotlib](https://pypi.org/project/matplotlib/) | 3.10.8 | Generate performance charts |

## Usage

```bash
python main.py
```

### Configuration

The following parameters can be adjusted at the top of [`main.py`](main.py):

| Variable | Default | Description |
|---|---|---|
| `TICKER` | `"AAPL"` | Yahoo Finance ticker symbol to backtest |
| `N` | `10` | SMA lookback window (in days) |

The data period is set to `"1y"` (one year) in the `yf.download()` call and can also be changed.

### Example Output

```
Total Return: 12.34
Sharpe Ratio: 0.056
Max Drawdown: -0.42
```

*(Values will vary depending on the ticker and the date the script is run.)*

## Project Structure

```
simple-backtesting-strategy/
├── main.py              # Backtesting logic, metrics, and plotting
├── requirements.txt     # Python dependencies
├── images/              # Generated charts (auto-created)
│   ├── cumulative_pnl.png
│   ├── daily_pnl.png
│   └── daily_position.png
├── task.pdf             # Original task specification
├── .gitignore
└── README.md
```
