# Peru El Niño Exposure Assessment

Course project for CLMT G5047 (Global Food Trade, Shocks & Migration), Fall 2026.
Full assignment brief: `reference/DataAnalysisProject_Instructions2026.pdf`. Read it before proposing any analysis, figure, or dataset.

## About me

- MA student (Climate and Society), new to R. My coding background is JavaScript for Webflow.
- I'm working in Positron. I run scripts myself, so explain what code does and why, in plain language.
- When you introduce a new function or concept, add a short comment explaining it. A JavaScript comparison helps when one fits.

## The project in one paragraph

An **exposure assessment, not an impact assessment**, of Peru's food system (coast and fisheries) to the 2026–27 El Niño. Trace the chain: ENSO signal → regional climate → production and trade → prices and access → household responses, including migration. The central question is where a drought or flood becomes hunger or displacement, and whose decisions shape that step (trigger vs. amplifier). Must compare at least **1997–98 and 2015–16**. Other useful events: the 2017 coastal floods (local coastal warming while the ONI stayed neutral) and the cancelled first 2023 anchoveta season. Peru-specific thread: anchoveta → fishmeal → aquaculture and livestock feed prices elsewhere.

## Key dates

- Wed 28 Oct: Milestone 1, one-page data summary (datasets downloaded and explored, data problems so far)
- Wed 4 Nov: Milestone 2, two draft figures + the AI conversation logs behind them
- Sun 15 Nov, 11:59 PM: final report (PDF)

## Folder structure

```
CLAUDE.md
reference/        assignment brief, Peru-crop-calendar_FAO.jpg, readings. Read-only.
data/raw/         original downloads. NEVER modify, overwrite, or delete.
data/processed/   cleaned data, written only by scripts
scripts/          numbered R scripts: 01_clean_oni.R, 02_clean_production.R, ...
outputs/          figures and tables
```

- Every file in `data/processed/` must be produced by a script in `scripts/`. No hand edits, no one-off cleaning outside a script.
- Scripts read from `data/raw/` or `data/processed/` and write to `data/processed/` or `outputs/`.
- Use relative paths from the project root (e.g. `data/raw/oni.csv`), never absolute paths.

## Code conventions

- R with tidyverse, native pipe `|>`. `library()` calls at the top of each script; never put `install.packages()` in a script.
- Keep it simple: event comparisons, correlations, and simple regressions are enough. Clarity over sophistication.
- Document each cleaning step in comments (what was dropped, renamed, filtered, and why). The appendix needs the data-cleaning steps.

## AI attribution (required by the assignment)

The report must show which code AI wrote. Mark every block you write:

```r
# --- AI-generated (Claude) ---
...code...
# --- end AI-generated ---
```

- If I edit an AI block, change the marker to `# --- AI-generated (Claude), edited by me ---`.
- Leave code I write myself unmarked, and never remove or change my markers.

## What you should and shouldn't do

**Do:** help with data import, cleaning, calculations (import dependency, supplier concentration), figures, debugging, and explaining results so I can interpret them myself.

**Don't:**
- Write report prose. The text of the report must be my own writing. You can explain, critique, or point out gaps in what I write, but don't draft sentences or paragraphs for the report.
- Invent or suggest citations. Every source must be real and read by me. If you mention a paper or report, say clearly that I need to find and verify it myself.
- Overstate attribution. El Niño shifts the odds of weather patterns; it doesn't cause any particular drought or flood. Flag it if my wording or a figure title implies otherwise.

## Figures

At least four in the final report: trade (flow map, network, Sankey, or ranked bar), map (exposure across the region), time series (with past El Niño events marked), and comparison (1997–98 vs. 2015–16, plus early 2026 data or forecasts where available).

Every figure needs: a title, axis labels with units, a legend where needed, a source line (caption), and readability when printed. Save to `outputs/` at 300 dpi, e.g. `ggsave(..., dpi = 300)`.

## Data sources (starting points from the brief)

| Need | Source |
|---|---|
| ENSO state and forecast | NOAA CPC (ONI or RONI; say which); IRI ENSO forecast plume; Columbia Climate School El Niño Hub |
| Rainfall | CHIRPS (Climate Hazards Center), monthly from 1981 |
| Food security outlooks | FAO GIEWS country briefs; IPC. FEWS NET does **not** cover Peru, so note this gap. |
| Production | FAOSTAT (crops and livestock); USDA PSD |
| Trade | FAOSTAT Detailed Trade Matrix |
| Prices | WFP VAM food prices; FAO GIEWS FPMA; World Bank Pink Sheet (global, incl. fishmeal) |
| Displacement and migration | IOM DTM; UNHCR Refugee Data Finder; national statistics |
| Remittances | World Bank / KNOMAD |

When a new dataset is added to `data/raw/`, add an entry to `reference/data_sources.md` with: organisation, dataset name, URL, access date, and any problems found (gaps, unit changes, missing years). This feeds the dataset citations, the Milestone 1 data summary, and the methods section.

Keep internal displacement and cross-border migration as separate variables and outcomes. Never combine them.
