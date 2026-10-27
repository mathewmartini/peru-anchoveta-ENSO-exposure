# Peru anchoveta and the 2026–27 El Niño: an exposure assessment

Course project for CLMT G5047, Global Food Trade, Shocks & Migration (Columbia University, Fall 2026).

An exposure assessment of Peru's coastal food system and anchoveta fishery to the 2026–27 El Niño, comparing past events (1997–98, 2015–16, 2017, 2023).

## Folder structure

| Folder | Contents |
| --- | --- |
| `data/raw/` | Original downloads, never edited |
| `data/processed/` | Cleaned data, written only by scripts |
| `scripts/` | Numbered R scripts, run in order (`01_…`, `02_…`) |
| `outputs/` | Figures and tables |
| `reference/` | Supporting material and the data source log |

## Raw data

| File | Source |
| --- | --- |
| `oni.ascii.txt` | NOAA Climate Prediction Center, Oceanic Niño Index (ONI) |
| `RONI_1950-present.csv` | NOAA, Relative Oceanic Niño Index (RONI) |
| `ICEN.txt` | ENFEN (Peru), Índice Costero El Niño (coastal El Niño index) |
| `Capture_2026.1.0/` | FAO, Global Capture Production, release 2026.1.0 |
| `PRODUCE Yearly Stat Books/` | Ministry of Production of Peru (PRODUCE), fisheries statistical yearbook |
| `BCRPData_*.csv` | Central Reserve Bank of Peru (BCRP), fisheries series |
| `CMO-Historical-Data-Monthly.xlsx` | World Bank, Commodity Price Data (Pink Sheet), monthly |
| `PFISHUSDM.csv`, `PSMEAUSDM.csv` | Fishmeal and soybean meal prices (IMF Primary Commodity Prices, via FRED) |

Full citations, URLs, access dates and known data problems are in `reference/data_sources.md`.

## Reproducing the analysis

Requires R with the tidyverse. Run the scripts in `scripts/` in numerical order from the project root; each reads from `data/` and writes to `data/processed/` or `outputs/`.

## AI use

Code written mostly by an AI assistant (Claude) is marked in each script with `# --- AI-generated (Claude) ---` comments, as the assignment requires.
