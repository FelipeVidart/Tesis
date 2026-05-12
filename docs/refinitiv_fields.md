# Refinitiv/LSEG Source Blocks

This table documents the main data blocks used by the thesis pipeline. It is a methodological map, not a redistribution of licensed data.

| Data block | Source | Original frequency | Final frequency | Main variables | Role in thesis |
|---|---|---|---|---|---|
| Corporate bonds | LSEG Workspace / Refinitiv exports | Bond-level daily or exported history | Monthly firm-level aggregates | OAS, YTM, maturity, coupon, ISIN, CUSIP, bond RIC | Provides the dependent variable and bond characteristics aggregated to the firm-month level. |
| Equity prices and returns | Refinitiv/LSEG API | Daily | Monthly | firm returns, adjusted prices, RIC, volatility inputs | Builds firm-level return measures, rolling risk measures, and market exposure inputs. |
| Market index / aggregate market shock | Refinitiv/LSEG API | Daily | Monthly | market index returns, `mkt_ret` | Measures aggregate market shocks used in the panel regressions. |
| Treasury / rates / macro-financial variables | Refinitiv/LSEG API and Workspace sources | Daily, monthly, or series-specific | Monthly | Treasury yields, rates, macro-financial controls | Supports spread construction, controls, and macro-financial context. |
| Credit factor / aggregate credit shock | Refinitiv/LSEG API and Workspace sources | Daily or monthly | Monthly | credit index returns or credit factor measures, `credit_shock` | Captures aggregate credit market conditions used in the credit-shock channel. |
| Fundamentals | Refinitiv/LSEG API | Quarterly or annual | Monthly forward-filled firm-level variables | leverage, liquidity, size, debt, assets, cash, revenue | Provides firm-level controls and heterogeneity variables. |
| GICS / sector identifiers | Refinitiv/LSEG identifiers and classification data | Point-in-time or periodic | Monthly firm-level identifiers | `gics_sector`, sector labels, industry groups | Supports sector classification, grouping, and market-share construction. |
| Firm identifiers | Refinitiv/LSEG identifiers and local harmonization | Point-in-time or source-specific | Monthly firm-level identifiers | `firm_id`, RIC, ISIN, CUSIP, ticker | Links bond, equity, fundamentals, sector, and macro blocks into one firm-month panel. |
