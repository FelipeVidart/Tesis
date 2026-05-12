# Data Directory

This directory documents the expected local data layout for the thesis pipeline. Licensed Refinitiv/LSEG datasets are not versioned in this repository.

Expected structure:

```text
data/
|-- raw/            # raw local Refinitiv/LSEG downloads
|-- intermediate/   # cleaned or harmonized intermediate files
|-- clean/          # final local analytical panel files
|-- inputs/         # manual Workspace exports and input templates
`-- sample/         # optional non-proprietary examples only
```

The `raw/`, `intermediate/`, `clean/`, `tmp/`, and licensed `inputs/` contents are excluded from Git because of data licensing restrictions and file size considerations.

Only documentation or templates that do not contain proprietary data should be versioned here. In particular, `data/inputs/README_inputs.md` and files under `data/inputs/templates/` may be committed when they contain no Refinitiv/LSEG observations, identifiers, or licensed values.
