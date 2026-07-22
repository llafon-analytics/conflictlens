# ConflictLens

ConflictLens is an open analytical notebook project about the structure of recorded conflict violence.

The public releases examine how recorded conflict deaths are distributed across years and country-years since 1989. The project is designed as a reproducible analytical companion to the published articles, not as a prediction system, causal model, legal classification, or perpetrator-attribution engine.

## Published articles

- **Seven years out of thirty-seven. Half the toll.**
  - Live article: [conflictlens.org/seven-years-out-of-thirty-seven-half-the-toll](https://conflictlens.org/seven-years-out-of-thirty-seven-half-the-toll/)
  - Article source: [`articles/01-seven-years-out-of-thirty-seven.md`](articles/01-seven-years-out-of-thirty-seven.md)
  - Reproduction notebook: [`notebooks/articles/01_seven_years_out_of_thirty_seven.ipynb`](notebooks/articles/01_seven_years_out_of_thirty_seven.ipynb)

- **The line is rising. But not everywhere.**
  - Live article: [conflictlens.org/the-line-is-rising-but-not-everywhere](https://conflictlens.org/the-line-is-rising-but-not-everywhere/)
  - Article source: [`articles/01a-the-line-is-rising-but-not-everywhere.md`](articles/01a-the-line-is-rising-but-not-everywhere.md)
  - Reproduction notebook: [`notebooks/articles/01a_the_line_is_rising_but_not_everywhere.ipynb`](notebooks/articles/01a_the_line_is_rising_but_not_everywhere.ipynb)

- **Two years, almost the same toll. Not the same shape.**
  - Live article: [conflictlens.org/two-years-almost-the-same-toll](https://conflictlens.org/two-years-almost-the-same-toll/)
  - Article source: [`articles/01b-two-years-almost-the-same-toll.md`](articles/01b-two-years-almost-the-same-toll.md)
  - Reproduction notebook: [`notebooks/articles/01b_two_years_almost_the_same_toll.ipynb`](notebooks/articles/01b_two_years_almost_the_same_toll.ipynb)

## Repository structure

```text
.
├── articles/
│   ├── 01-seven-years-out-of-thirty-seven.md
│   ├── 01a-the-line-is-rising-but-not-everywhere.md
│   └── 01b-two-years-almost-the-same-toll.md
├── data/
│   └── README.md
├── docs/
│   ├── data-sources.md
│   ├── interpretation-guardrails.md
│   └── methodology.md
├── figures/
│   ├── seven-years-out-of-thirty-seven/
│   ├── the-line-is-rising-but-not-everywhere/
│   └── two-years-almost-the-same-toll/
├── notebooks/
│   ├── articles/
│   │   ├── 01_seven_years_out_of_thirty_seven.ipynb
│   │   ├── 01a_the_line_is_rising_but_not_everywhere.ipynb
│   │   └── 01b_two_years_almost_the_same_toll.ipynb
│   └── core/
│       ├── 01_conflictlens_foundation_eda_en.ipynb
│       ├── 02_conflictlens_analysis_unit_year_panel_build.ipynb
│       └── 03_conflictlens_country_year_analysis.ipynb
├── CITATION.cff
├── LICENSE
├── CONTENT_LICENSE.md
└── requirements.txt
```

## Notebooks

The notebooks are intentionally published as analytical artefacts. They are not merely appendix material: they contain the data profiling, panel-building decisions, descriptive analysis, robustness checks, and article-specific validation steps behind the project.

| Notebook | Role |
|---|---|
| `notebooks/core/01_conflictlens_foundation_eda_en.ipynb` | Initial inventory and exploratory profiling of the available conflict-related datasets. |
| `notebooks/core/02_conflictlens_analysis_unit_year_panel_build.ipynb` | Construction of the analysis-ready unit-year panel, including source joins, crosswalk handling, coverage flags and zero-fill safeguards. |
| `notebooks/core/03_conflictlens_country_year_analysis.ipynb` | Main descriptive analysis notebook: conflict structure, concentration, temporal dynamics, macro-context axes, civilian exposure and robustness checks. |
| `notebooks/articles/01_seven_years_out_of_thirty_seven.ipynb` | Reproduces the first article's concentration measures, validation checks and figures. |
| `notebooks/articles/01a_the_line_is_rising_but_not_everywhere.ipynb` | Reproduces the second article's recent annual totals, country-year concentration, category composition, summary table and figures. |
| `notebooks/articles/01b_two_years_almost_the_same_toll.ipynb` | Reproduces the third article's annual-total comparison, concentration checks and five article-facing figures. |

## Reproducibility

The raw datasets are not redistributed in this repository. See [`data/README.md`](data/README.md) and [`docs/data-sources.md`](docs/data-sources.md) for expected sources, filenames and placement.

Recommended setup:

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
# .venv\Scripts\Activate.ps1  # Windows PowerShell

python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Recommended execution order:

```text
1. notebooks/core/01_conflictlens_foundation_eda_en.ipynb
2. notebooks/core/02_conflictlens_analysis_unit_year_panel_build.ipynb
3. notebooks/core/03_conflictlens_country_year_analysis.ipynb (for the full core analysis)
```

After Notebook 02, run any publication-specific notebook as needed; they are alternative reproductions, not sequential dependencies:

- `notebooks/articles/01_seven_years_out_of_thirty_seven.ipynb`
- `notebooks/articles/01a_the_line_is_rising_but_not_everywhere.ipynb`
- `notebooks/articles/01b_two_years_almost_the_same_toll.ipynb`

All article notebooks expect the analysis-ready panel generated by Notebook 02.

## Interpretation guardrails

The most important analytical convention is that a country-year contributor is not a perpetrator. A share of annual deaths is an arithmetic contribution to a coded analytical unit and year; it is not a finding about responsibility, victims, targeting, nationality, legal classification, or historical interpretation.

See [`docs/interpretation-guardrails.md`](docs/interpretation-guardrails.md) for the full set of public interpretation rules.

## Data scope

The published articles' headline figures are computed from UCDP data only. ACLED, V-Dem and WDI are part of the wider ConflictLens country-year panel and are used for complementary context, benchmarking or later analytical axes, not as the primary conflict-death count in the published articles.

The published articles cover 1989–2025, which follows the start of UCDP's event-level global coverage. The project does not make claims about earlier mass-fatality conflicts outside this data window.

## License

This repository uses a dual-license structure:

- Code and notebook code cells are released under the MIT License. See [`LICENSE`](LICENSE).
- Articles, documentation and figures are released under Creative Commons Attribution 4.0 International. See [`CONTENT_LICENSE.md`](CONTENT_LICENSE.md).
- Third-party datasets are not redistributed here and remain governed by their respective providers' terms.

## Citation

If you use or refer to this repository, please cite it using [`CITATION.cff`](CITATION.cff).
