# VaR of an Equity Portfolio

[`var_analysis.ipynb`](var_analysis.ipynb) — weekly returns for **AAPL, META, NVDA, TSLA** from `data/spx_returns_weekly.xlsx`.

## Contents

**1. Diversification**
- 1.1 unconditional volatility, empirical VaR(.05), empirical CVaR(.05) per stock (`.quantile`).
- 1.2 equally-weighted portfolio — same stats vs the singles; diversification via imperfect correlation.
- 1.3 drop the most volatile asset (weight → 0, i.e. risk-free) and measure the risk it actually contributed.

**2. Dynamic measures**
- 2.1 rolling vol (m=26, data through t−1), zero mean, normal VaR/CVaR with z₍.₀₅₎ = −1.65, τ = 1; annualized and compared to 1.2.
- 2.2 hit-test backtest (realized return below predicted VaR) for expanding vs rolling volatility.

## Run

```bash
pip install -r ../requirements.txt
jupyter notebook var_analysis.ipynb   # then Run All
```
