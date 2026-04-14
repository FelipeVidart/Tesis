
# S&P 500 Credit Spreads Thesis

Undergraduate finance thesis on corporate bond credit spreads, aggregate market and credit shocks, and firm-level exposure using Python and Refinitiv data.

## Overview

This repository contains the analytical workflow developed for an undergraduate thesis in Finance.

The project studies how aggregate market and credit shocks — together with firm-level heterogeneity in exposure — are reflected in corporate bond credit spreads for firms in the S&P 500.

The repository is intended to show the research and analytical process behind the thesis: data extraction, cleaning, panel construction, econometric estimation, and output generation.

## Research Question

How are aggregate market and credit shocks, together with heterogeneous firm-level exposure to those shocks, reflected in corporate bond credit spreads of S&P 500 firms?

## Why this project matters

This repository is relevant as a professional portfolio project because it combines:

- financial research design
- Python applied to finance
- multi-source data cleaning and integration
- panel dataset construction
- econometric modeling
- interpretation of results in a corporate finance / fixed income context

## Project Scope

- **Universe:** S&P 500 firms
- **Period:** 2015–2025
- **Unit of analysis:** firm-month
- **Main outcome variable:** corporate bond credit spreads (OAS)

The final analytical dataset combines bond-level, equity, macro-financial, and firm-level information into a firm-month panel used for panel regressions.

## Data

The project relies on data obtained through **Refinitiv / LSEG Workspace**.

Because of licensing restrictions, raw proprietary datasets are **not distributed** in this repository. The repo is designed to document the workflow and analytical structure rather than redistribute restricted data.

## Repository Structure

    .
    ├── notebooks/
    │   ├── 01_descarga_datos.ipynb
    │   ├── 02_construccion_panel.ipynb
    │   └── 03_runer_econometrico.ipynb
    ├── src/
    ├── data/
    │   ├── inputs/
    │   └── sample/
    ├── outputs/
    │   ├── figures/
    │   └── tables/
    ├── docs/
    ├── requirements.txt
    ├── .gitignore
    └── README.md

## Workflow

The project follows three main stages:

### 1. Data extraction
**`01_descarga_datos.ipynb`**

Builds the firm universe and retrieves the raw financial data required for the project.

### 2. Panel construction
**`02_construccion_panel.ipynb`**

Cleans, harmonizes, and merges bond, equity, macro-financial, and firm-level data into a final firm-month panel.

### 3. Econometric estimation
**`03_runer_econometrico.ipynb`**

Runs the main panel specifications and generates tables, figures, diagnostics, and robustness outputs.

## Empirical Approach

The empirical strategy is based on panel regressions designed to distinguish between:

- aggregate shocks that vary over time and affect all firms
- firm characteristics that amplify or attenuate the transmission of those shocks
- firm-specific residual risk

The specification sequence includes:

- a baseline model with fixed effects
- macro-financial specifications
- aggregate market shock models
- heterogeneous exposure to market shocks
- aggregate credit shock models
- heterogeneous exposure to credit shocks
- a joint specification combining both channels

## Main Tools

- Python
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- statsmodels
- linearmodels
- Refinitiv / LSEG Workspace

## Reproducibility

This repository documents the full analytical workflow, but complete replication requires valid access to Refinitiv / LSEG Workspace data.

To install dependencies locally:

```bash
pip install -r requirements.txt
```

If API credentials or local paths are needed, they should be configured locally and excluded from version control.

## Notes

- This repository is presented as an academic and analytical portfolio project.
- Some intermediate files, proprietary datasets, and local environment files are intentionally excluded.
- The written thesis reflects the final academic document, while this repository reflects the analytical workflow behind it.

## Author

Felipe Vidart  
Undergraduate Finance Thesis  
Universidad de San Andrés
