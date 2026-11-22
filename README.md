# 6BUIS017W – S&P 500 Market Analysis and Stock Segmentation Using RFM

Notebook: `6BUIS017W_SP500_RFM.ipynb` (Google Colab, Python 3.13, pandas 2.2.3, yfinance 0.2.66)

## How to run
Open the notebook in Colab and select **Runtime → Restart session and run all**.
The notebook loads the preserved data snapshots from the `Data/` folder of this repository,
so results are reproducible without re-downloading from Yahoo Finance.

## Data
- `Data/prices_raw_2021-01-01_2025-01-01_retrieved_2026-10-21.csv.gz` – raw daily prices (snapshot)
- `Data/sp500_constituents_2026-10-21.csv` – S&P 500 constituent list (Wikipedia)
- `Data/exclusion_log_1_1.csv`, `exclusion_log_1_2.csv`, `inclusion_exclusion_log.csv` – exclusions
- `Data/features_final.csv` – feature table (485 shares)
- `Data/cluster_assignments.csv` – Ward and K-means cluster assignments
-  Other CSVs – validation checks, k-selection tables, profiles and correlations

## Study settings
Study period 1 Jan 2021 – 31 Dec 2024; benchmark ^GSPC; observation date 31 Dec 2024;
485 shares retained; random seed 42.

`figures/` contains all charts used in the report.
