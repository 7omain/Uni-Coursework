# 6BUIS017W – S&P 500 Market Analysis and Stock Segmentation Using RFM

Segmentation of S&P 500 shares using two feature sets – weekly risk-return (mean weekly return, beta) and an adapted RFM model based on high-volume trading days – clustered with Ward agglomerative clustering and K-means.

Notebook: `6BUIS017W_SP500_RFM.ipynb`

## How to run
1. Open the notebook in Google Colab.
2. Select **Runtime → Restart session and run all**.

The notebook loads the preserved price snapshot and constituent list from the `Data/` folder of this repository, so results are reproducible without re-downloading from Yahoo Finance or Wikipedia. A fresh download only runs if the snapshot cannot be found.

## Environment
Python 3.13, pandas 2.2.3, yfinance 0.2.66, plus scikit-learn, SciPy, NumPy and matplotlib as provided by Google Colab.

## Data and provenance
- **Prices:** Yahoo Finance via yfinance (`auto_adjust=False`, so both Close and Adjusted Close are kept), retrieved 21 October 2026 and saved before any cleaning as `Data/prices_raw_2021-01-01_2025-01-01_retrieved_2026-10-21.csv.gz`.
- **Constituents:** Wikipedia "List of S&P 500 companies", first retrieved 21 October 2026. Because early runs re-read Wikipedia, the stored copy
  (`Data/sp500_constituents_2026-10-21.csv`) reflects a November 2026 retrieval, it is now loaded from this repository so results do not change between runs.
- **Exclusions:** `Data/exclusion_log_1_1.csv`, `Data/exclusion_log_1_2.csv` and `Data/inclusion_exclusion_log.csv` record every excluded share and the reason.

## Study settings
- Study period: 1 January 2021 – 31 December 2024 (1,005 trading days, 207 aligned weeks)
- Benchmark: S&P 500 index (^GSPC)
- RFM observation date: 31 December 2024 (60-session window from 7 October 2024)
- Shares: 503 retrieved → 485 retained
- Random seed: 42 (K-means with 50 initialisations)

## Repository contents
- `Data/features_final.csv` – feature table (one row per share, 485 shares)
- `Data/cluster_assignments.csv` – Ward and K-means cluster assignments for all four baseline solutions, plus the R + F sensitivity solution
- `Data/` – other CSVs: validation checks, k-selection tables, cluster profiles, correlations, seed stability and sector composition
- `Figure/` – all charts used in the report
