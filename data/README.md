# Data directory

This repository does not redistribute raw third-party datasets.

To reproduce the notebooks, download the required source files from their official providers and place them in a local data directory following the conventions below.

Do not commit raw, processed, merged, or analysis-ready data files derived from third-party datasets unless their redistribution terms have been checked explicitly. This includes merged panels, intermediate exports, parquet files, CSV extracts, Excel exports, and any file that contains source-provider data or source-derived records.

## Recommended local layout

```text
data/
├── raw/
│   ├── ucdp/
│   ├── acled/
│   ├── vdem/
│   ├── wdi/
│   └── auxiliary/
└── README.md
```

`data/raw/` is ignored by Git.

## Main source files referenced by the notebooks

The exact filenames may reflect the export date used during the original analysis.

### UCDP

- `ged261-csv.zip`
- `organizedviolencecy-261-csv.zip`
- `ucdp-onesided-261-csv.zip`
- `ucdp-actor-261-csv.zip`

### ACLED

- `number_of_reported_fatalities_by_country-year_as-of-26Jun2026.xlsx`
- `number_of_reported_civilian_fatalities_by_country-year_as-of-26Jun2026.xlsx`
- `number_of_political_violence_events_by_country-year_as-of-26Jun2026.xlsx`
- `number_of_events_targeting_civilians_by_country-year_as-of-26Jun2026.xlsx`
- `number_of_political_violence_events_by_country-month-year_as-of-26Jun2026.xlsx`
- `_aggregated_data_up_to_week_of-2026-06-20.xlsx`

### V-Dem

- `V-Dem-CY-Full+Others-v16.csv`, or the local filename used in the notebooks:
  - `Others-v16.csv`

### World Bank WDI

- `world_bank_wdi_panel_long.csv`
- `world_bank_wdi_panel_wide.csv`

### Auxiliary or exploratory sources

These sources may be profiled in Notebook 01 or used for context and later extensions:

- `EPR-2021.csv`
- `SVAC_3.3_complete.xlsx`
- `SVAC_3.3_conflictyears.xlsx`
- `persons_of_concern.csv`
- `persons_of_concern_demographics.csv`
- `country_crosswalk_manual.csv`

## Generated files

Notebook 02 generates the analysis-ready panel used downstream, especially:

```text
outputs/02_analysis_unit_year_panel_analysis_ready.parquet
```

Notebook 03 and the article notebook generate additional diagnostic tables and figures.

Generated outputs are ignored by Git unless explicitly copied into the public `figures/` or `articles/` folders.

## Publication rule

The public repository may include:

- notebooks;
- code;
- articles;
- documentation;
- aggregate figures;
- instructions for downloading and placing source data.

The public repository should not include, without explicit source-by-source license review:

- raw datasets;
- processed datasets;
- merged country-year panels;
- analysis-ready parquet or CSV files;
- large table exports derived from provider datasets;
- source extracts that could substitute for downloading the original data.
