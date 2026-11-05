# Calgary Building Permits Analysis

What do half a million building permits tell us about speed, cost and growth in Calgary? This project works with the City of Calgary Building Permits open dataset in two notebooks.

## Notebooks

1. `01_data_audit_and_preparation.ipynb`: downloads a dated snapshot of the table, audits it (29 findings), decides how to handle each finding and saves a checked analysis dataset.
2. The analysis notebook, which reads the processed dataset, will be added to this repository.

## Data

- `data/raw/building_permits_2026-11-05.csv.gz`: snapshot of 2026-11-05 with the 21 columns used (503,411 rows).
- `data/processed/building_permits_analysis_2026-11-05.parquet`: processed dataset (40 columns, 503,411 rows), with the raw columns kept next to their `_clean` versions.

## Reproducing the results

Python with pandas, requests and pyarrow. Run the notebook from the root of the repository: it uses the snapshot in `data/raw` and downloads the table from the City portal only if that file is missing.

## Source

City of Calgary Open Data, Building Permits (dataset c2es-76ed): https://data.calgary.ca/resource/c2es-76ed. The use of the data is subject to the licence of the portal.

## Author

Emely Lephilibert
