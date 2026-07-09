# Methodology

This document summarizes the public analytical workflow behind ConflictLens.

## Project status

ConflictLens is a descriptive, open-notebook conflict-analysis project. Its purpose is to inspect structure, concentration, intensity, diffusion and source behavior in conflict-related data. It is not a causal inference system, a forecasting model, a legal classification tool, or a perpetrator-attribution framework.

## Analytical grain

The validated analytical grain used after panel construction is:

```text
analysis_unit_id + year
```

This is intentionally broader than a strict contemporary ISO3 country-year panel. Some historical, composite or non-standard units may carry real conflict signal while not mapping cleanly to a present-day ISO3 code.

`country_iso3` is therefore treated as an attribute when available, not as the universal analytical key.

## Notebook workflow

### 1. Foundation EDA

Notebook:

```text
notebooks/core/01_conflictlens_foundation_eda_en.ipynb
```

Purpose:

- inventory available datasets;
- profile file sizes, schemas, temporal coverage and geographic coverage;
- inspect granularity and identifier compatibility;
- document quality risks and source-specific constraints;
- stop before making causal claims or final analytical choices.

### 2. Analysis-unit-year panel build

Notebook:

```text
notebooks/core/02_conflictlens_analysis_unit_year_panel_build.ipynb
```

Purpose:

- construct the analysis-ready panel;
- normalize country/unit labels;
- apply manual crosswalk decisions where needed;
- retain source-specific coverage flags;
- distinguish `NA` from observed or defensible zero values;
- export the final analysis-ready panel consumed by Notebook 03.

Preferred output:

```text
outputs/02_analysis_unit_year_panel_analysis_ready.parquet
```

### 3. Country-year / analysis-unit-year analysis

Notebook:

```text
notebooks/core/03_conflictlens_country_year_analysis.ipynb
```

Purpose:

- analyze conflict incidence, prevalence, intensity and concentration;
- inspect distribution shape and extreme observations;
- examine temporal transitions, conflict spells, escalation and de-escalation;
- compare UCDP and ACLED as distinct source families;
- explore macro-context gradients under a restricted macro universe;
- explore civilian exposure and one-sided violence indicators under a conflict universe;
- document robustness checks and pruning decisions.

### 4. Article validation notebook

Notebook:

```text
notebooks/articles/01_seven_years_out_of_thirty_seven.ipynb
```

Purpose:

- recalculate the headline figures used in the article;
- export the figures included in the article;
- assert key numerical claims before publication;
- keep the article traceable to the analytical panel.

## Source hierarchy

For the first article, UCDP is the primary source for headline conflict-death figures.

ACLED, V-Dem and WDI are part of the wider ConflictLens panel, but they are not used as the primary source for the first article's headline death totals.

## Universe rules

The notebooks keep separate analytical universes:

| Universe | Role |
|---|---|
| `analysis_conflict_universe` | Used for conflict structure, UCDP/ACLED comparisons and civilian exposure. |
| `analysis_core_macro_universe` | Used for macro-context comparisons requiring more comparable country-year coverage. |
| `unit_exists_in_year` | Prevents pre-existence or invalid rows from being silently treated as peaceful zero observations. |

## `NA` and zero handling

The project treats missingness as analytically meaningful. `NA` and `0` are not interchangeable.

Zero-filled metrics are used only under guarded conditions where a source universe and unit-year existence logic make a zero interpretation defensible for the specific descriptive purpose. Residual missingness outside the relevant source universe is not silently interpreted as peace or absence of violence.

## Counts and rates

Raw counts and normalized rates answer different questions.

- Raw deaths show where the recorded toll accumulates.
- Per-capita rates help compare relative intensity across differently sized populations.
- Neither should be treated as a standalone severity ranking.

## Descriptive categories

Labels such as genocide, civil war, interstate war or civilian-exposure rupture are descriptive analytical labels used to explain different shapes of violence. They are not legal determinations and do not rank moral gravity.

## Reproducibility limits

This repository does not redistribute raw datasets. Exact reproduction requires downloading source data from the original providers and placing it according to `data/README.md`.

Because some sources are periodically revised, future downloads may not reproduce every number exactly unless the same source versions are used.
