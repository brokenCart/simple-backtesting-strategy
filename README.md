# 📊 Moving Average Backtesting Strategy
A Python implementation of a simple moving-average trading strategy that backtests historical stock data, computes performance metrics, and generates visualizations of positions and PnL.

## Features
- Downloads historical stock data using yfinance
- Moving average trading signal generation
- Daily and cumulative PnL calculation
- Performance metrics:
  - Sharpe Ratio
  - Maximum Drawdown
  - Total Return
- Visualization of:
  - Cumulative PnL
  - Daily positions
  - Daily PnL

## Installation
```bash
git clone https://github.com/brokenCart/simple-backtesting-strategy.git
cd simple-backtesting-strategy
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

## Run
```bash
python main.py
```

## Project Structure
```
.
├── images
│   ├── cumulative_pnl.png
│   ├── daily_pnl.png
│   └── daily_position.png
├── main.py
├── README.md
├── requirements.txt
└── task.pdf
```

## Strategy Overview
The strategy uses a simple moving average (SMA) of the closing price:
- Go **long (+1)** when price ≥ moving average  
- Go **short (-1)** when price < moving average  
Daily PnL is calculated based on position and price changes, and performance is evaluated using standard risk metrics.

## Metrics Computed
- **Total Return** — final cumulative PnL  
- **Sharpe Ratio** — risk-adjusted return  
- **Maximum Drawdown** — largest peak-to-trough decline  
