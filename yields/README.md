# Treasury Yields

Exercise from the [FINM 25000 course](https://markhendricks.github.io/finm-25000/index.html).

## Setup

```
pip install -r ../requirements.txt
```

The notebook reads data from `data/treasury_quotes_2025-04-30.xlsx`. Open `treasury_yields.ipynb` and **Run All**.

## Data

- `data/treasury_quotes_2025-04-30.xlsx` — Treasury security quotes as of April 30, 2025 (bills, notes, bonds, and TIPS across all maturities).

## Results at a glance

### 1.1 — Stylised 30-year bond (3% coupon, face 100)

- **Price given YTM = 5%:** 69.09
- **YTM given Price = 87:** 3.7231%

### 1.2 — Selected quotes (semiannually-spaced notes)

- Calculated YTM matches the dataset's provided YTM closely across all 20 issues.
- **Max absolute error: 3.15 bps** (shortest-maturity note, ~0.5yr TTM); **mean absolute error: 0.38 bps**.
- The small residual reflects rounding in the data's TTM column vs. exact calendar-day conventions.

### 2.1 — Yield curve shape (nominal securities)

- The yield curve as of April 30, 2025 is upward-sloping from ~4.2% at the short end to ~4.1–4.2% at the long end, with a pronounced inversion/trough around 2–3 years (~3.6%).

### 2.2 — YTM across all nominal coupon bonds

- YTM calculated successfully for all 345 nominal coupon-bearing issues (notes and bonds).
- All issues in the dataset have a provided YTM — no missing values among nominals.
- **Mean absolute error: 10.2 bps; max absolute error: 202.6 bps** (concentrated in very short TTM issues, < 0.3yr, where the semiannual rounding approximation breaks down most severely).

### 2.3 — T-bill discount yields

- Discount yields computed for all 51 T-bills (identified by `type == 'bill'` or `cpn_rate == 0`).
- Discount yields range from **0% (overnight bill) to ~4.16%**, clustering tightly around **4.1% for maturities of 1–6 months**.
- Bond-equivalent yields run slightly above the discount yields as expected; both track the dataset's provided YTM closely.