# Calgary Building Permits Analysis

What do half a million building permits tell us about speed, cost and growth in Calgary? This project works with the City of Calgary Building Permits open dataset in two notebooks.

## Notebooks

1. `01_data_audit_and_preparation.ipynb`: downloads a dated snapshot of the table, audits it (29 findings), decides how to handle each finding and saves a checked analysis dataset.
2. `02_permit_cost_speed_and_growth.ipynb`: reads the processed dataset from this repository and analyses the wait for a permit, the cost of the projects, the volume of applications over the years and the seasons, and the location of the activity. It ends with a summary of each chapter and five recommendations for a permit office.

## Data

- `data/raw/building_permits_2026-11-05.csv.gz`: snapshot of 2026-11-05 with the 21 columns used (503,411 rows).
- `data/processed/building_permits_analysis_2026-11-05.parquet`: processed dataset (40 columns, 503,411 rows), with the raw columns kept next to their `_clean` versions.

## Reproducing the results

- **Notebook 1:** Python with pandas, requests and pyarrow. Run the notebook from the root of the repository: it uses the snapshot in `data/raw` and downloads the table from the City portal only if that file is missing.
- **Notebook 2:** runs in Google Colab or any Jupyter environment with Python 3. The libraries are pandas, numpy, pyarrow, matplotlib, scipy, statsmodels, lifelines, contextily and requests, and the setup cell installs the ones that Colab does not include. It needs internet access to read the processed dataset from this repository, to download the Consumer Price Index table of Statistics Canada and to load the map tiles. The quantile regressions of section 2.8 are the slowest step and can take a few minutes.

## Sources

- City of Calgary Open Data, Building Permits (dataset c2es-76ed): https://data.calgary.ca/resource/c2es-76ed. The use of the data is subject to the licence of the portal.
- Statistics Canada, Consumer Price Index, annual average, table 18-10-0005-01, used to express costs in constant dollars.
- Esri base maps, used for the maps of notebook 2.

## Author

Emely Lephilibert
