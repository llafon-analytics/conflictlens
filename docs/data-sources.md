# Data sources

This document lists the main data sources referenced by ConflictLens.

Raw data is not redistributed in this repository. Users should download the source files directly from the providers and respect each provider's terms of use.

## Primary conflict source for the first article

| Source | Version / file | Role in ConflictLens |
|---|---|---|
| UCDP Georeferenced Event Dataset | `ged261-csv.zip` / v26.1 | Primary event-level source for organized-violence deaths used in the first article's headline calculations. |
| UCDP Organized Violence country-year dataset | `organizedviolencecy-261-csv.zip` / v26.1 | Country-year aggregate source used for cross-checking annual totals. |
| UCDP One-sided Violence dataset | `ucdp-onesided-261-csv.zip` / v26.1 | Used to inspect one-sided violence and civilian-focused patterns. |
| UCDP Actor dataset | `ucdp-actor-261-csv.zip` / v26.1 | Profiled for source understanding and potential actor-level extensions. |

Provider: UCDP, Uppsala University  
Website: <https://uu.se/en/department/peace-and-conflict-research/research/ucdp>

## Complementary conflict benchmark

| Source | Example local files | Role in ConflictLens |
|---|---|---|
| ACLED | `number_of_reported_fatalities_by_country-year_as-of-26Jun2026.xlsx` | Complementary benchmark for political violence and reported fatalities. |
| ACLED | `number_of_reported_civilian_fatalities_by_country-year_as-of-26Jun2026.xlsx` | Civilian-fatality benchmark. |
| ACLED | `number_of_political_violence_events_by_country-year_as-of-26Jun2026.xlsx` | Event-count benchmark. |
| ACLED | `number_of_events_targeting_civilians_by_country-year_as-of-26Jun2026.xlsx` | Civilian-targeting benchmark. |

Provider: Armed Conflict Location & Event Data Project  
Website: <https://acleddata.com>

ACLED is not treated as a drop-in replacement for UCDP. The two sources have different definitions, coverage choices, coding rules and update behavior.

## Political and institutional context

| Source | Example local file | Role in ConflictLens |
|---|---|---|
| V-Dem | `Others-v16.csv` / V-Dem-CY-Full+Others v16 | Country-year political and institutional context used for macro-context axes. |

Provider: V-Dem Institute, University of Gothenburg  
Website: <https://v-dem.net>

## Socioeconomic context

| Source | Example local files | Role in ConflictLens |
|---|---|---|
| World Bank WDI | `world_bank_wdi_panel_long.csv`, `world_bank_wdi_panel_wide.csv` | Socioeconomic and demographic context used for rates and macro comparison. |

Provider: World Bank, World Development Indicators  
Website: <https://databank.worldbank.org/source/world-development-indicators>

## Auxiliary / exploratory sources

These sources may appear in Notebook 01 as part of the foundation EDA and source inventory:

| Source | Example local files | Role |
|---|---|---|
| EPR | `EPR-2021.csv` | Ethnic Power Relations source, profiled as possible contextual data. |
| SVAC | `SVAC_3.3_complete.xlsx`, `SVAC_3.3_conflictyears.xlsx` | Sexual Violence in Armed Conflict source, profiled as possible thematic extension. |
| UNHCR / displacement-related data | `persons_of_concern.csv`, `persons_of_concern_demographics.csv` | Humanitarian and displacement context, profiled as possible later extension. |

## Source-use statement for the first article

The first article, **"Seven years out of thirty-seven. Half the toll."**, computes its concentration and peak-year figures from UCDP data only.

ACLED, V-Dem and WDI are part of the wider ConflictLens panel but are not used for that article's headline conflict-death count.
