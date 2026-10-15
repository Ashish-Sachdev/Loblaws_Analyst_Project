# Loblaw Financial Analysis - Project Proposal

## Page 1: Project idea and scope

### Purpose

Build an independent portfolio dashboard that turns Loblaw Companies Limited public financial disclosures into a clear view of growth, profitability and cash generation. Owner: Ashish Sachdev. Status: planning only; no financial findings have been calculated.

### Problem and audience

Financial information is available in reports and supplementary slides, but comparing periods requires assembling figures and checking their definitions. The intended audience is a financial analyst, investor or hiring reviewer. The project does not claim Loblaw lacks internal dashboards or that it is affiliated with Loblaw.

### MVP scope

Use fiscal years 2022-2025. Begin with annual figures; add quarterly analysis only after annual reconciliation. Analyze the consolidated company, rather than individual Loblaws stores. Use Python/pandas for cleaning, DuckDB SQL for analysis, and Power BI for a three-page dashboard. Do not add forecasting, a website, or competitor comparisons to the first version.

### Business questions

1. How fast is revenue growing, and is earnings growth keeping pace? 2. How much profit is retained from each dollar of sales? 3. Does the business generate operating cash alongside reported earnings? 4. How much operating cash remains after capital investment? 5. If comparable disclosures exist, how do food and drug same-store sales growth differ? These are descriptive questions; financial statements alone cannot establish why prices changed or prove pricing misconduct.

### Source plan

Primary source: https://www.loblaw.ca/en/investors-reports/ (checked 11 October 2026). The page lists 2022-2025 annual and quarterly reports and supplementary slides. Download reports during implementation and capture document URL, reporting period, page/table, access date, units and definition for every observation. No numbers are invented in this starter.

---

## Page 2: KPI definitions and answer method

### K1 | Revenue and revenue growth

Revenue in CAD millions. Year-over-year growth = (current revenue / prior-year comparable revenue - 1) x 100. Answers question 1. Show a revenue trend and growth labels; a rising level with falling growth means expansion is slowing. Retrieve 2021 as a comparator if calculating 2022 growth.

### K2 | Net earnings and earnings growth

Use consolidated profit for the period attributable to all owners, with an explicit continuing/total-operations basis, rather than silently substituting earnings available to common shareholders. Growth = (current / prior - 1) x 100 only where prior earnings are positive; otherwise show the absolute change and an explanatory note. Answers question 1. Report the earnings-versus-revenue growth gap in percentage points.

### K3 | Net profit margin

Comparable consolidated profit / consolidated revenue x 100. Use matching scopes: continuing profit with continuing revenue, or total profit with total revenue where disclosed. Answers question 2. A margin of 3% would mean $3 of profit per $100 of revenue; this is an illustration, not a Loblaw result.

### K4 | Operating cash flow and cash conversion

Cash generated from operating activities in CAD millions. Operating cash flow / matching consolidated profit is a secondary diagnostic, only where earnings are positive and the scopes match. Answers question 3. Review working-capital movements before interpreting a change as better or worse earnings quality.

### K5 | Cash after capital spending

Analyst-defined cash after capex = operating cash flow - cash purchases of property, plant and equipment - cash purchases of intangible assets. Store purchases as positive outflows. Answers question 4. This is not automatically Loblaw reported free cash flow; lease payments, acquisitions and other investing outflows are excluded and must be disclosed.

### K6 | Same-store sales growth (optional)

Use the reported food and drug retail same-store sales growth percentages and preserve the company definition. Do not derive these from consolidated revenue. Answers question 5 only if comparable figures are disclosed. Treat as a supporting indicator; do not infer store-level sales or profit.

### What can be answered now?

The proposal defines how to answer each question. Numerical answers remain pending source extraction and validation. A dashboard will show missing values as unavailable, never zero; zero denominators yield no ratio. Percent changes and percentage-point margin changes must be labeled differently.

---

## Page 3: Implementation, dashboard and acceptance

### Data and comparability rules

Retain original reported figures and revised comparative figures separately. Prefer a consistent restated series only when comparable disclosures support it; otherwise present separate bases with notes. Record fiscal start/end dates and number of weeks, since fiscal periods may differ in length. Flag discontinued operations, changes in reporting scope and share splits if EPS is added later. Never combine reported and adjusted measures without labeling and reconciliation.

### Three dashboard pages

Page 1 - Is growth becoming more profitable? Revenue, earnings, growth and profit margin by fiscal year. Page 2 - Do earnings turn into cash? Operating cash flow, capex, analyst-defined cash after capex and conditional cash conversion. Page 3 - What should we question? Comparable food/drug same-store growth where available, reporting changes, source references and a short evidence-based findings panel. Include year filters and visible units on every page.

### Starter repository

docs contains the proposal, KPI dictionary, business questions and source guidance. data/raw stores untouched source documents; data/interim stores reviewed extraction; data/processed stores analysis-ready tables. src holds future Python ETL; sql holds future queries; notebooks holds exploratory work; dashboards/powerbi holds the future report; reports/figures and reports/findings hold outputs; tests holds future validation checks. Empty folders use .gitkeep. No ETL or dashboard is implemented yet.

### Execution sequence

Session 1: collect annual reports and extract 2024-2025 figures with source pages. Session 2: reconcile scopes and extend through 2022, with a 2021 comparator if needed. Session 3: clean with pandas and calculate metrics in SQL. Sessions 4-5: build Power BI and write three defensible findings. Keep the first version annual; quarterly figures are an extension, not a requirement.

### Acceptance criteria

Every displayed number traces to a document and table/page. Revenue and profit definitions match in ratios. Cash amounts reconcile to cash-flow statements. Annual and quarterly/YTD values cannot be accidentally aggregated together. KPI calculations are independently spot-checked. Dashboard includes units, fiscal periods, data basis and limitations. README shows screenshots, reproduction steps and three verified findings once implemented.

### First concrete task

Extract a small 2024-2025 comparison for revenue, consolidated profit, operating cash flow and cash purchases of property/equipment and intangibles. Prove the definitions and source references first. Then expand the period range. The goal is a credible analysis, not a large collection of charts.

