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
- `etf-arbitrage/data/etf_arb_data.xlsx` — **not** in the course [Box data folder](https://uchicago.app.box.com/s/h3z027v9rjbil3pzx4zystwozorie6f9) (rolling-vintage file); download it and drop it in that folder. The notebook runs in a placeholder-NAV fallback until then.

## Results at a glance (VaR, stocks AAPL / META / NVDA / TSLA)

- **Diversification (1.2):** EW-portfolio weekly vol **4.32%** vs **5.78%** average of the singles; VaR/CVaR similarly compressed. Driven by an average pairwise correlation of **0.40**.
- **Most volatile asset (1.3):** TSLA. Zeroing its 1/4 weight cuts portfolio vol **~30%**, yet it adds only **1.32%** weekly vol to the portfolio vs **8.03%** stand-alone — marginal risk ≪ stand-alone risk.
- **Conditional, end of sample (2.1):** annualized vol **24.7%** (vs 31.2% unconditional), normal VaR(.05) **−5.6%**, normal CVaR(.05) **−7.0%**.
- **Hit test (2.2):** expanding vol **4.4%**, rolling vol (m=26) **4.0%** — both near the 5% target.
