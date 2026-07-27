# Homework 6 — FINM 25000

Two exercises from the [FINM 25000 course](https://markhendricks.github.io/finm-25000/index.html):

| Folder | Exercise |
|---|---|
| [`var-equity-portfolio/`](var-equity-portfolio/) | [VaR of an Equity Portfolio](https://markhendricks.github.io/finm-25000/exercises/VaR%20of%20Equity%20Portfolio.html) |
| [`etf-arbitrage/`](etf-arbitrage/) | [ETF Arbitrage](https://markhendricks.github.io/finm-25000/exercises/ETF%20Arbitrage.html) |

## Setup

```bash
pip install -r requirements.txt
```

Each subfolder holds one Jupyter notebook and its own `data/` folder. Open the notebook and **Run All**.

## Data

- `var-equity-portfolio/data/spx_returns_weekly.xlsx` — included (weekly SPX returns).
- `etf-arbitrage/data/etf_arb_data.xlsx` — included (Bloomberg-sourced prices/NAV for SPY, HYG, GBTC). Not in the shared course [Box data folder](https://uchicago.app.box.com/s/h3z027v9rjbil3pzx4zystwozorie6f9) (rolling-vintage file); committed here directly.

## Results at a glance (VaR, stocks AAPL / META / NVDA / TSLA)

- **Diversification (1.2):** EW-portfolio weekly vol **4.32%** vs **5.78%** average of the singles; VaR/CVaR similarly compressed. Driven by an average pairwise correlation of **0.40**.
- **Most volatile asset (1.3):** TSLA. Zeroing its 1/4 weight cuts portfolio vol **~30%**, yet it adds only **1.32%** weekly vol to the portfolio vs **8.03%** stand-alone — marginal risk ≪ stand-alone risk.
- **Conditional, end of sample (2.1):** annualized vol **24.7%** (vs 31.2% unconditional), normal VaR(.05) **−5.6%**, normal CVaR(.05) **−7.0%**.
- **Hit test (2.2):** expanding vol **4.4%**, rolling vol (m=26) **4.0%** — both near the 5% target.

## Results at a glance (ETF Arbitrage, SPY / HYG)

- **SPY premium (1.1):** mean **0.30 bps**, std **4.23 bps**, range **−79.8 to +90.0 bps** — tight except in brief stress windows.
- **Creation trade (1.2):** at a 0.50% premium on a 50,000-share unit (NAV ≈ $737), gross profit ≈ **$184k**.
- **Breakeven (1.3):** ≈ **3.8 bps** after a $3,000 creation fee + 3 bps trading cost — same order as SPY's own std dev, so only tail dislocations clear it.
- **HYG 2020 (2.1):** deepest discount **−127.4 bps on 2020-03-20**; largest premium **+458.4 bps on 2020-04-09** (Fed corporate-credit-facility expansion).
