# S&P 500 Credit Spreads Thesis - Methodological Companion

This repository is the methodological companion to the approved Undergraduate Thesis in Finance:

> "Shocks agregados de mercado y crédito, exposición diferencial y spreads de crédito: evidencia de empresas del S&P 500"

The repository documents the computational pipeline used to download, organize, clean, integrate, and analyze licensed Refinitiv/LSEG data for the thesis. It is intended to support methodological traceability and conditional reproducibility for authorized users, not to redistribute proprietary datasets.

The empirical question is:

> How are aggregate market and credit shocks, and firm-level heterogeneity in exposure to those shocks, reflected in corporate bond credit spreads of S&P 500 firms?

Core design features:

- Universe: firms in the S&P 500.
- Period: 2015-2025.
- Unit of observation: firm-month.
- Main dependent variable: option-adjusted spread (OAS), aggregated at the firm-month level.
- Data source: Refinitiv/LSEG only, through API downloads and authorized Workspace exports.

## Data Availability And Licensing

All raw market, bond, equity, fundamentals, identifier, and macro-financial data used in the thesis come from Refinitiv/LSEG. These data are subject to license restrictions and are not redistributed in this repository.

The repository does not include:

- Raw Refinitiv/LSEG downloads.
- Manual Workspace exports.
- Proprietary firm-level, bond-level, or observation-level panel datasets.
- Local credentials or API keys.

Authorized users must obtain the data directly through their own Refinitiv/LSEG access and place local inputs in the expected folders described in `data/README.md` and `data/inputs/README_inputs.md`.

Aggregated tables and figures may be versioned when they do not disclose proprietary observation-level data and when doing so is consistent with applicable license restrictions.

## Reproducibility Scope

This is not a public complete replication package. Full replication requires:

- Authorized access to Refinitiv/LSEG Workspace and APIs.
- A valid local API key configured outside version control.
- Manual Workspace exports where required by the pipeline.
- The same notebook execution order used in the thesis.

Within those constraints, the repository allows readers to audit:

- The computational workflow used to obtain and organize source data.
- The cleaning and integration logic used to construct the firm-month panel.
- The construction of variables used in the thesis.
- The panel regression workflow and diagnostic output generation.

The approved thesis results are not being revised here. The repository is curated to document the existing workflow.

## Pipeline Overview

The pipeline is organized around three notebooks:

| Step | Notebook | Purpose |
|---|---|---|
| 1 | `notebooks/01_descarga_datos.ipynb` | Download and organize Refinitiv/LSEG data. |
| 2 | `notebooks/02_construccion_panel.ipynb` | Clean, harmonize, merge, and construct the firm-month panel. |
| 3 | `notebooks/03_runer_econometrico.ipynb` | Estimate panel models and generate regression tables, figures, and diagnostics. |

The workflow documents how the thesis pipeline:

1. Downloads and organizes data from Refinitiv/LSEG.
2. Cleans and integrates bond, equity, macro-financial, fundamentals, sector, and identifier sources.
3. Constructs the final firm-month panel.
4. Estimates panel models.
5. Generates tables, figures, and diagnostics used for thesis reporting.

See `docs/lineage_log.csv` for a compact lineage map across inputs, outputs, and notebooks.

## Repository Structure

```text
.
|-- notebooks/
|   |-- 01_descarga_datos.ipynb
|   |-- 02_construccion_panel.ipynb
|   `-- 03_runer_econometrico.ipynb
|
|-- data/
|   |-- README.md
|   |-- inputs/
|   |   |-- README_inputs.md
|   |   `-- templates/
|   |-- raw/            # local only, not versioned
|   |-- intermediate/   # local only, not versioned
|   |-- clean/          # local only, not versioned
|   `-- sample/         # optional non-proprietary samples only
|
|-- docs/
|   |-- reproducibility_note.md
|   |-- lineage_log.csv
|   |-- refinitiv_fields.md
|   |-- data_dictionary.csv
|   `-- data_dictionary.md
|
|-- outputs/
|   |-- tables/
|   |-- figures/
|   `-- results/
|
|-- src/
|-- .env.example
|-- .gitignore
|-- requirements.txt
|-- LICENSE
`-- README.md
```

## Setup

Create a Python environment and install dependencies:

```bash
python -m venv venv
pip install -r requirements.txt
```

Configure credentials locally by creating a `.env` file in the project root:

```text
EIKON_APP_KEY=your_refinitiv_or_lseg_app_key_here
```

Do not commit `.env` or any credentials.

## Execution Order

The notebooks are designed to be run sequentially by an authorized user with local access to the licensed inputs:

1. `notebooks/01_descarga_datos.ipynb`
2. `notebooks/02_construccion_panel.ipynb`
3. `notebooks/03_runer_econometrico.ipynb`

The third notebook name is preserved as used in the approved thesis workflow.

## Econometric Framework

The empirical analysis estimates panel models relating firm-month credit spreads to aggregate market and credit shocks, heterogeneous exposure, firm controls, and fixed effects as implemented in the thesis notebooks.

The baseline structure can be summarized as:

```text
spread_it = alpha
          + beta_1 * market_shock_t
          + beta_2 * credit_shock_t
          + beta_3 * exposure_it * market_shock_t
          + beta_4 * exposure_it * credit_shock_t
          + controls_it
          + firm fixed effects
          + time controls or time fixed effects
          + error_it
```

This README describes the workflow and does not modify the thesis specifications, results, or reported estimates.

## Recommended Next Steps

- Add non-proprietary templates under `data/inputs/templates/` if useful for documenting manual Workspace export formats.
- Review whether any existing observation-level outputs should be moved out of version control under the applicable Refinitiv/LSEG license.
- Add a short notebook header to each notebook only if future documentation review requires it.
- TODO: consider renaming `03_runer_econometrico.ipynb` in a future cleanup after updating all references and confirming no path dependencies.

## Author

Undergraduate Thesis in Finance

Universidad de San Andrés

2025-2026
