# ETF Arbitrage

[`etf_arbitrage.ipynb`](etf_arbitrage.ipynb) — premium/discount dynamics for **SPY** and **HYG**.

## Data

Needs `data/etf_arb_data.xlsx` (tabs `descriptions`, `prices`, `nav`; tickers SPY, HYG, GBTC). This file is **not** in the course Box data folder — download it and drop it in `./data/`. Without it, the arbitrage arithmetic (1.2, 1.3) still runs on a placeholder NAV; the data-driven stats and plots (1.1, 2.1) light up once the file is present.

## Contents

**1. The SPY premium** — 1.1 daily premium/discount, SPY summary in bps + time series; 1.2 the AP creation trade at a 0.50% premium on one 50,000-share creation unit; 1.3 breakeven premium under a $3,000 creation fee + 3 bps trading cost, and why SPY stays pinned to NAV.

**2. HYG in March 2020** — 2.1 HYG premium/discount through 2020 with the deepest discount / largest premium and dates; 2.2 the redemption trade and why the discount was not free money; 2.3 whether price or NAV was the accurate signal, and what April 2020 shows.

## Run

```bash
pip install -r ../requirements.txt
jupyter notebook etf_arbitrage.ipynb   # then Run All
```
