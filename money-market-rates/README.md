# Money-Market Rates

Analysis of key money-market reference rates — SOFR, Fed Funds, and the 3-month T-bill yield — and a comparison of interest-rate autocorrelation with SPY equity returns.

## Setup

```
pip install -r requirements.txt
```

Place both data files in the `data/` subfolder, then open the notebook and **Run All**.

## Data

- `data/ref_rates.xlsx` — Daily SOFR, Fed Funds Effective (DFF), and 3-month T-bill yield (DTB3) from FRED. Covers 2018–2026.
- `data/spy_data_daily.xlsx` — Daily SPY prices and total returns from Yahoo Finance via yfinance. Covers 1994–2026.

## Contents

| Section | Description |
|---|---|
| **1. Time Series Plot** | All three rates plotted together over the full sample |
| **2. Correlation Analysis** | Pairwise correlations in levels and in day-over-day differences |
| **3. SOFR Autoregression** | AR(1) for SOFR — estimated β, R², and interpretation of rate persistence |
| **4. SPY Autoregression** | AR(1) for SPY returns and prices — contrast with interest-rate behavior |

## Key Results

- In **levels**, all three rates are nearly perfectly correlated (≥ 0.99), driven by the common Fed policy cycle. In **differences**, correlations drop substantially — T-bill yields are market-determined and deviate more on a daily basis than the two overnight rates.
- **SOFR** has an AR(1) β ≈ 1.000 and R² ≈ 1.000. Interest rates are highly persistent (near unit-root), so today's rate is an excellent predictor of tomorrow's level — but this is a trivial forecast that conveys no directional information.
- **SPY returns** have β ≈ 0 and R² ≈ 0 — no meaningful autocorrelation, consistent with the Efficient Market Hypothesis. **SPY prices**, like interest rate levels, show β ≈ 1 and R² ≈ 1 and are non-stationary.
