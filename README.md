# Simple Backtesting Strategy

Simple Backtesting Strategy is a Python application for backtesting quantitative trading strategies against historical stock market data.

## Description

This project backtests a Simple Moving Average (SMA) crossover trading strategy using historical price data fetched from Yahoo Finance. The strategy evaluates daily stock closing prices against an N-day SMA to generate long (+1) and short (-1) positions. It evaluates strategy performance by calculating cumulative returns, risk-adjusted returns via the Sharpe ratio, and peak-to-trough risk via maximum drawdown, while producing chart visualizations saved as output artifacts.

## Key Features

- **Automated Data Fetching**: Retrieves historical price data directly from Yahoo Finance.
- **SMA Crossover Strategy**: Implements a configurable N-day Simple Moving Average rule to generate long and short trading positions.
- **Performance Analytics**: Calculates core quantitative metrics including Total Return, Sharpe Ratio, and Maximum Drawdown.
- **Automated Visualization**: Generates and exports plots for cumulative PnL, daily positions, and daily PnL to an output directory.
- **Fast Package Management**: Managed with `uv` for fast dependency resolution and environment synchronization.

## Installation

### Prerequisites

- Python 3.13 or higher
- [uv](https://docs.astral.sh/uv/) package manager

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/brokenCart/simple-backtesting-strategy.git
   cd simple-backtesting-strategy
   ```

2. Install dependencies and set up the environment using `uv`:
   ```bash
   uv sync
   ```

## Usage

Execute the main script using `uv`:

```bash
uv run main.py
```

### Configuration Options

You can adjust parameters at the top of `main.py`:

- `TICKER`: Target stock symbol (default: `"AAPL"`).
- `N`: Moving average lookback period in days (default: `10`).

## Project Structure

```
simple-backtesting-strategy/
├── main.py              # Main script containing strategy logic, metrics calculation, and plotting
├── pyproject.toml       # Project metadata and dependency definitions
├── uv.lock              # Lockfile for reproducible environment resolution
├── images/              # Generated output charts
│   ├── cumulative_pnl.png
│   ├── daily_pnl.png
│   └── daily_position.png
└── README.md            # Project documentation
```
