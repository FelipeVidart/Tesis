# Manual Data Inputs

This folder documents licensed manual inputs that must be exported by an authorized user from LSEG Workspace / Refinitiv. These files are required to reproduce the analytical workflow, conditional on authorized access to licensed data, but they cannot be redistributed through this repository.

The Python pipeline expects selected manual input files to exist locally when constructing the final firm-month panel. The files themselves are not included in Git.

## Why Manual Inputs Are Required

Some datasets used in the thesis workflow are obtained through LSEG Workspace exports rather than through an automated Refinitiv Python API call.

Examples include:

- Historical bond yields for selected corporate bonds.
- Bond-level metadata needed for identifier matching.
- Excel exports produced through LSEG Workspace tools.

Because these datasets originate from licensed Refinitiv/LSEG sources, they must remain local to authorized users.

## Expected Folder Structure

```text
data/inputs/
`-- bonds_empresas/
    |-- ConsumerStaples_and_Discretionary.xlsx
    |-- Energy.xlsx
    |-- Financials.xlsx
    |-- Health_Care.xlsx
    |-- Industrials.xlsx
    |-- Technology_and_comms.xlsx
    `-- Utilities_and_Real_Estate.xlsx
```

The pipeline reads files from `data/inputs/bonds_empresas/` during panel construction.

## Expected Files

The following licensed Excel exports are expected locally in `data/inputs/bonds_empresas/`:

- `ConsumerStaples_and_Discretionary.xlsx`
- `Energy.xlsx`
- `Financials.xlsx`
- `Health_Care.xlsx`
- `Industrials.xlsx`
- `Technology_and_comms.xlsx`
- `Utilities_and_Real_Estate.xlsx`

These files typically include bond-level information such as:

- Yield to maturity.
- Bond identifiers, including ISIN and CUSIP.
- Issuer identifiers.
- Pricing information.
- Maturity and coupon characteristics.

The exact fields must match the exports and column names expected by the panel-construction notebook. Do not rename columns expected by the pipeline.

## How To Regenerate The Files

1. Open LSEG Workspace / Refinitiv with authorized credentials.
2. Use the relevant bond search or data export tools.
3. Query the corporate bonds corresponding to the firms in the thesis universe.
4. Export the required results to Excel `.xlsx` files.
5. Save the files inside `data/inputs/bonds_empresas/` using the filenames listed above.

## Important Notes

- These files are required by `notebooks/02_construccion_panel.ipynb`.
- If the files are missing, panel construction will fail with a file-not-found error.
- These datasets are not distributed because of Refinitiv/LSEG licensing restrictions.
- Do not commit the Excel exports, raw data, proprietary identifiers beyond documentation needs, or any licensed observation-level data.

## Reproducibility Statement

The repository provides code and documentation required to reproduce the analytical workflow, conditional on authorized access to licensed data. Users must rely on their own Refinitiv/LSEG access and credentials to regenerate the raw and manual input datasets used in the thesis.
