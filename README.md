# Momentum Crossover Strategy (Single Ticker)

A compact, beginner-friendly trading research project that tests a classic **moving-average crossover** on one stock (e.g., `AAPL`) using daily data.

**Goal:** Go **long** when the **fast SMA** is above the **slow SMA**, otherwise stay **flat**.  
We evaluate returns out-of-sample with simple trading costs and report **CAGR, Sharpe, Max Drawdown, and Turnover**.

> **Disclaimer:** Educational project only. Not investment advice.

---

## Tools Used
- Python
- pandas, numpy
- matplotlib

---

## Data
- **Source:** Kaggle — “S&P 500 stock data” (file often named `all_stocks_5yr.csv`)
- **Fields used:** `date`, `ticker`, `close` (others optional)
- Place the CSV at `data/all_stocks_5yr.csv` (or update the path in the notebook)

---

## Project Steps
1. **Load & clean** the Kaggle dataset; select one `TICKER` (e.g., `AAPL`) and sort by date.
2. Compute **SMA(FAST)** and **SMA(SLOW)** (defaults: 50/200).
3. Build **signal**: `1` when `SMA_FAST > SMA_SLOW`, else `0`.  
   (We **shift by 1 day** to avoid look-ahead.)
4. Compute **log returns**, apply position **signal**, and subtract **simple trading costs** only when the position changes.
5. Report metrics (**CAGR, Sharpe, MaxDD, Turnover**) and plot **Equity**, **Drawdown**, and **Price + SMAs**.
6. (Optional) Run a small **parameter grid** (e.g., 20/100, 50/150, 50/200).

---

## Results (example)

Results will vary by ticker, sample, fees, and SMA windows. Below is an example table you can replace with your own:

| Metric            | Value |
|-------------------|-------|
| CAGR              | 12.3% |
| Sharpe            | 0.88  |
| Max Drawdown      | -20.4%|
| Turnover / year   | 3.1   |
