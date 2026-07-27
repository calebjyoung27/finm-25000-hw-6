# ETF Arbitrage

[`etf_arbitrage.ipynb`](etf_arbitrage.ipynb) — premium/discount dynamics for **SPY** and **HYG**.

## Data

`data/etf_arb_data.xlsx` (tabs `descriptions`, `prices`, `nav`; tickers SPY, HYG, GBTC), Bloomberg-sourced. Not in the shared course Box data folder (rolling-vintage file) — included here directly. Without it, the arbitrage arithmetic (1.2, 1.3) falls back to a placeholder NAV; with it, all cells run on real data.

## Contents

**1. The SPY premium** — 1.1 daily premium/discount, SPY summary in bps + time series (mean **0.30 bps**, std **4.23 bps**, range **−79.8 to +90.0 bps**); 1.2 the AP creation trade at a 0.50% premium on one 50,000-share creation unit (NAV ≈ $737, gross profit ≈ $184k); 1.3 breakeven premium ≈ **3.8 bps** under a $3,000 creation fee + 3 bps trading cost — on the same order as SPY's own std dev, so only stress-day dislocations clear it.

**2. HYG in March 2020** — 2.1 HYG premium/discount through 2020: deepest discount **−127.4 bps on 2020-03-20**, largest premium **+458.4 bps on 2020-04-09**; 2.2 the redemption trade and why the discount was not free money; 2.3 whether price or NAV was the accurate signal, and what April 2020 shows.

## Run

```bash
pip install -r ../requirements.txt
jupyter notebook etf_arbitrage.ipynb   # then Run All
```
