# Reproducibility Note

This repository documents the computational workflow used for the approved thesis on aggregate market and credit shocks, differential firm exposure, and S&P 500 corporate credit spreads.

It contains:

- Notebooks that document the data download, data organization, panel construction, econometric estimation, and output generation workflow.
- Documentation describing expected licensed inputs, pipeline lineage, source blocks, and selected analytical variables.
- Aggregated tables, figures, and diagnostics when they do not disclose proprietary observation-level data and when versioning them is consistent with applicable license restrictions.

It does not contain:

- Raw Refinitiv/LSEG downloads.
- Manual LSEG Workspace exports.
- Proprietary bond-level, firm-level, or observation-level datasets.
- Refinitiv/LSEG credentials, API keys, or local `.env` files.

Complete replication requires authorized access to Refinitiv/LSEG Workspace and APIs, together with the user's own credentials and licensed data exports. The repository should therefore be interpreted as a methodological and computational companion to the thesis, not as a public complete replication package.

Within these licensing constraints, the repository allows readers to audit the pipeline, the data lineage, and the logic used to construct variables and estimation inputs.
