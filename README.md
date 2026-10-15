# Loblaw Financial Analysis

Independent portfolio project by Ashish Sachdev using public disclosures of Loblaw Companies Limited. Not affiliated with or endorsed by Loblaw.

**Status: starter repository.** No data, calculated findings, pipeline or dashboard exists yet.

## Objective

Explore growth, profitability and cash generation across fiscal years 2022-2025 using Python/pandas, DuckDB SQL and Power BI.

## Start here

- [Three-page proposal](docs/project_proposal.pdf)
- [Editable proposal](docs/project_proposal.md)
- [Business questions](docs/business_questions.md)
- [KPI dictionary](docs/kpi_dictionary.md)
- [Sources and comparability](docs/data_sources.md)

## Structure

| Folder | Purpose |
| --- | --- |
| docs/ | Proposal, KPI definitions and source guidance |
| data/raw/ | Untouched public source documents |
| data/interim/ | Reviewed extracted observations |
| data/processed/ | Clean, comparable analysis tables |
| src/ | Future Python extraction and transformation |
| sql/ | Future DuckDB analysis queries |
| notebooks/ | Exploratory analysis |
| dashboards/powerbi/ | Future Power BI report |
| reports/figures/ | Dashboard screenshots and charts |
| reports/findings/ | Verified findings and limitations |
| tests/ | Future reconciliation and data checks |

## First milestone

Extract and reconcile 2024-2025 revenue, consolidated profit, operating cash flow and cash capex with source page references. Extend to 2022 only after matching the reporting scopes.

## Data integrity

Do not invent missing figures, mix annual and YTD data, treat missing values as zero, or combine continuing-operations revenue with total-operations earnings. Reported and adjusted measures require separate labels. Source documents retain their owners' rights.

Implementation and installation instructions will be added when executable code exists.
