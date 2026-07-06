# Bitcoin Price Analysis — 2025

Case study project analyzing a full year (2025) of daily Bitcoin (BTC-USD) price data — price
trends, volatility, and seasonality — built into a set of interactive Plotly charts. Built as
part of my analytics portfolio at [gimeno.tech](https://www.gimeno.tech).

## Business problem

Bitcoin's price swings dramatically over short windows. This project explores 2025's daily
price action to surface trend, scale, and volatility patterns that are useful context for
anyone tracking crypto markets.

## Approach

1. **Ingest** daily BTC-USD OHLCV data for 2025.
2. **Clean** the data: parse timestamps, keep the relevant price/volume columns, sort
   chronologically.
3. **Explore**: price overview (Open/High/Low/Close), a candlestick chart, a linear-vs-log
   scale comparison of the close price, monthly average close price, and daily percent change.
4. **Export** each chart as a standalone interactive HTML file for the portfolio site.

## Repo structure

```
bitcoin-price-analysis/
├── data/incoming/     Raw source CSV (2025 daily BTC-USD OHLCV)
├── notebooks/         End-to-end analysis notebook
```

The interactive charts this notebook produces are published live on the portfolio site rather
than duplicated in this repo — running the notebook regenerates them locally as standalone
HTML files in a git-ignored `charts/` folder.

## Running it

```bash
pip install -r requirements.txt
jupyter notebook notebooks/Bitcoin_Price_Analysis_2025.ipynb
```

Running all cells top to bottom reproduces every chart (saved to a local `charts/` folder,
git-ignored) from the raw data in `data/incoming/`. Paths are resolved relative to the project
root, so it runs the same whether you launch it from the repo root or from inside `notebooks/`.

## Key findings

- BTC ranged roughly from the high-$80Ks to the low-$120Ks over 2025, with a clear mid-year
  run-up followed by a pullback into year end.
- The log-scale view flattens the early-year volatility relative to the linear view, which is
  the more honest way to compare percentage moves across the year.
- Daily percent-change swings of 5%+ in either direction occur repeatedly throughout the year —
  this is a genuinely volatile asset even on a "normal" trading day.

## Notes

This project originally started from a practice/training notebook that had been run against
placeholder price data unrelated to actual Bitcoin prices (the numbers didn't match real BTC
history at all). This repo's notebook was rebuilt from scratch against the real 2025 BTC-USD
daily series so the analysis and charts reflect actual market data.
