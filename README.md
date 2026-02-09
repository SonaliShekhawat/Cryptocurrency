# Cryptocurrency Dashboard

This repository contains a Power BI project that provides a live, interactive dashboard for cryptocurrency market analysis. Data is ingested from live API sources, cleaned and transformed in Power Query Editor, and analyzed in Power BI using DAX measures and visualizations.

---

**Planned steps (what I implemented, step-by-step)**
1. Data acquisition: connect to live CoinGecko API and load raw JSON/CSV into Power Query.
2. Data inspection: examine schemas, identify missing fields and inconsistent data types.
3. Data cleaning & normalization: apply Power Query transformations to standardize fields.
4. Data modelling: create relationships and a star-like model for efficient DAX calculations.
5. Calculated columns & measures: author DAX for KPIs, percent changes, and ranking logic.
6. Visual design: build pages with KPI cards, time-series charts, tables, and filters.
7. Validation & QA: validate measures, spot-check sample rows, and verify refresh behavior.
8. Documentation: capture the pipeline, analysis steps, limitations and next steps (this file).

---

## Data Source
- Source type: Live data (CoinGecko API)
- Data format: JSON (API) / saved raw exports in `Data/`
- Data fields collected (examples): `id`, `symbol`, `name`, `current_price`, `market_cap`, `ath`, `atl`, `price_change_percentage_24h`, `price_change_percentage_7d`, `last_updated`, plus metadata and categories

## Data Cleaning (Power Query Editor)
Step-by-step Power Query actions applied:
- Connect to API endpoint and expand nested records.
- Promote headers and ensure consistent column names.
- Remove unnecessary columns (API metadata not used in analysis).
- Convert data types: text → numeric, datetime parsing for `last_updated`.
- Trim and clean text fields; standardize `symbol` and `name` casing.
- Remove exact duplicates and keep latest records by `last_updated`.
- Handle missing values: replace, impute or flag depending on field importance.
- Normalize currencies/units if needed (e.g., convert tiny units to readable numbers).
- Create derived columns in Power Query when simpler than DAX (e.g., `PriceUSD = current_price` if unit conversions required).
- Load a cleaned staging table and a separate historical table for time-series analysis.

## Data Model
- Tables: `Raw_API`, `Cleaned_Coins`, `Historical_Price` (example names)
- Keys: `id` (coin id) as primary join key across tables
- Relationships: one-to-many from `Cleaned_Coins` → `Historical_Price`
- Date table: created or imported to support time intelligence functions in DAX

## Analysis performed (detailed, step-by-step)
Below are the exact analyses implemented in the dashboard and how they were built.

1) KPI calculations
 - `Coin Count` — DAX measure counting unique `id` values from `Cleaned_Coins`.
 - `Market Cap` — SUM of `market_cap` for the selected filter context.
 - `Current Price` — latest `current_price` via LASTNONBLANK or MAX on `last_updated`.
 - `Price Change 24h %` — either taken directly from API or computed using DAX as
	 $$\frac{Price_{now}-Price_{24h\_ago}}{Price_{24h\_ago}}\times100$$
 - `Price Change 7d %` — similar DAX measure using 7-day lookback.

2) Time-series analysis
 - Built `Historical_Price` table with daily snapshots (timestamped).
 - Used line charts with the date table for continuous time axis.
 - Created moving averages (7-day, 30-day) DAX measures to smooth volatility.
 - Yearly aggregation for `All Time High by Year` using MAX aggregation grouped by YEAR.

3) Ranking and comparative analysis
 - Ranking measure: `RANKX` over `market_cap` or `% change` to list top-N coins.
 - Comparison tables for wrapped/staked tokens filtered by `category` or name pattern (e.g., contains "wrapped" or "staked").
 - Calculated columns for asset classification (Wrapped / Staked / Native) using conditional logic in Power Query or DAX.

4) Volatility & distribution analysis
 - Volatility measures: standard deviation of daily returns computed in DAX across chosen window.
 - Histogram or distribution visuals to show price-change distribution across coins.

5) Correlation and co-movement (optional/implemented where data exists)
 - Pairwise correlation measures between selected assets using Pearson correlation computed via DAX or exported to Analysis/ for deeper stats.

6) Outlier detection and event flags
 - Flags for 24h spikes/drops (threshold-based) using conditional DAX or Power Query rules.
 - Marked top gainers/losers on the main page for quick inspection.

7) Filtering and interactivity
 - Slicers: `Name`, `Category`, `Date Range`, `Market Cap Range`
 - Cross-filtering between charts and detail tables for drill-through analysis.

## Visualizations (pages & components)
- Overview page: KPI cards, market-cap donut, top movers table.
- Time-series page: multi-select line charts with moving averages and volume.
- Comparison page: side-by-side tables for wrapped vs staked tokens.
- Detail page: single-coin performance with historical chart and key metrics.
- Export/Report page: static snapshots and explanation notes.

## Validation & Quality Assurance
- Spot-checked random coins against CoinGecko web interface for price and market-cap parity.
- Verified `last_updated` propagation through ETL to ensure freshest snapshot shown.
- Confirmed DAX measures with manual calculations on sample rows.

## Known limitations
- API rate limits may affect frequency of live refreshes.
- Some historical data gaps where exchanges or the API do not provide full daily snapshots.
- Correlation measures are sensitive to missing observations—use with caution.




