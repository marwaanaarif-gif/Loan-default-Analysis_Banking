# 🏦 Loan Default Analysis - Power BI Dashboard

A multi-page Power BI dashboard analyzing loan default patterns across a banking dataset. The report segments borrowers by employment type, age group, credit score, education level, marital status, and income bracket to uncover risk concentrations and track year-over-year default trends.

---

| Page | Description |
|------|-------------|
https://github.com/marwaanaarif-gif/Housing-market-overview-power-bi/blob/main/housing%20market%20overview.png | House Market Overview |
https://github.com/marwaanaarif-gif/Housing-market-overview-power-bi/blob/main/Sales%20overview.png | Sales Overview |
https://github.com/marwaanaarif-gif/Housing-market-overview-power-bi/blob/main/house%20type%20overview.png| House Type Overview |
```

---

## 📊 Report Pages

### Page 1 — Loan Default Overview

The entry page provides a macro-level read on loan volumes and default rates across the portfolio.

| Visual | Type | Description |
|--------|------|-------------|
| Loan Amount vs Purpose | Line Chart | Total loan amount distributed across loan purposes (e.g. personal, auto, mortgage) |
| Avg Income by Employment Type | Line Chart | Compares average borrower income across employment categories |
| Default Rate (%) by Employment Type | Line Chart | Highlights which employment segments carry the highest default risk |
| Average Loan by Age Group | Line Chart | Shows how loan size scales across borrower age buckets |
| Default Rate by Year | Line Chart | Tracks how the overall default rate has shifted across calendar years |

---

### Page 2 — Applicant Demographics and Financial Profile

Drills into borrower-level characteristics to surface behavioral and financial patterns by credit score, age, education, and family status.

| Visual | Type | Description |
|--------|------|-------------|
| Median Loan Amt by Credit Category | Line Chart | Maps median borrowing levels to credit score bins |
| Avg Loan Amt (High Credit) by Age Group & Marital Status | Donut Chart | Breaks down average loan size for high-credit borrowers by age and marital status |
| Total Amt (Middle-Aged) vs Credit Score | Clustered Column Chart | Compares total loan volume for middle-aged borrowers across credit bins, split by dependent status |
| Total Amt (Adults/Older) vs Credit Score | Line Chart | Same credit bin analysis scoped to older adult borrowers |
| Total Loans by Education Type | Line Chart | Distribution of total loan counts across education levels |

---

### Page 3 — Financial Risk Overview

Time-series risk analysis and a decomposition tree to investigate the structural drivers of loan volume.

| Visual | Type | Description |
|--------|------|-------------|
| YOY Loan Amount Change by Year | Line Chart | Year-over-year percentage change in total loan issuance |
| YOY Default Loan Change by Year | Line Chart | Year-over-year change in defaulting loan volume — the headline risk signal |
| Decomposition Tree: Loan Amount | Decomposition Tree | Breaks total loan amount down by Income Bracket → Employment Type for root-cause analysis |

---

## 🧮 DAX Measures

All custom measures are housed in a dedicated `MEASURE` table for clean separation from raw data.

| Measure Name | Purpose |
|---|---|
| `SUM OF LOAN AMOUNTS` | Total loan volume across the filtered context |
| `AVG INCOME` | Average borrower income |
| `Default Rate(%) by Employment Type` | Percentage of defaulted loans scoped to each employment category |
| `Average Loan by Age Group` | Mean loan amount per age bucket |
| `Default Rate by Year` | Annual default rate calculated across the full portfolio |
| `MEDIAN LOAN AMT` | Median loan amount — used to reduce distortion from outlier loans |
| `AVG Loan Amount (High Credit)` | Average loan amount filtered to high credit-score borrowers only |
| `Adults Total Loan` | Total loan amount scoped to the middle-aged segment |
| `Total Amount Older` | Total loan amount scoped to the older adult segment |
| `YOY LOAN AMOUNT CHANGE` | Year-over-year delta in total loan issuance |
| `YOY Defaulters` | Year-over-year change in the count or volume of defaulting loans |

---

## 🗂️ Data Fields

The report is built on a single fact table: `Loan_default`.

### Key Columns

| Column | Description |
|--------|-------------|
| `LoanID` | Unique identifier per loan record |
| `LoanAmount` | Disbursed loan value |
| `LoanPurpose` | Category of loan (e.g. personal, mortgage, auto) |
| `EmploymentType` | Borrower employment classification |
| `Age Groups` | Calculated age bucket (e.g. young adult, middle-aged, senior) |
| `YEAR` | Loan issuance year — used for trend analysis |
| `CREDIT BINS` | Credit score range category (e.g. poor, fair, good, excellent) |
| `MaritalStatus` | Borrower marital status |
| `HasDependents` | Boolean flag — whether borrower has financial dependents |
| `Education` | Highest education level of the borrower |
| `Income Bracket` | Grouped income tier used in decomposition analysis |

---

## 💡 Key Findings Surfaced

- **Employment type is a primary default risk driver** — the default rate chart reveals meaningful spread across employment categories, with certain types consistently underperforming
- **Credit score segmentation matters beyond just approval** — median loan amounts vary significantly across credit bins, with high-credit borrowers drawing larger averages
- **Dependents affect middle-aged borrower behavior** — the clustered column chart on Page 2 shows loan volume differences between borrowers with and without dependents within the same credit bin
- **YOY default trends are non-linear** — the Page 3 time series indicates default rates don't simply track loan volume growth, suggesting structural risk shifts over time
- **Income bracket and employment type together explain most loan volume variance** — the decomposition tree anchors this finding with a drillable breakdown

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Report building, data modelling, DAX authoring |
| DAX | All custom KPI and ratio calculations |
| Power Query (M) | Data transformation and column preparation |
| MS Excel | Data cleaning |

---

## 🚀 How to Open

1. Download `Loan_default_analysis__BANKING_PROJECT_.pbix`
2. Open in **Power BI Desktop** (free download from Microsoft)
3. Navigate between the three report pages using the page tabs at the bottom
4. Use the decomposition tree on Page 3 to interactively drill into loan amount by income bracket and employment type
5. To connect your own dataset, go to **Home → Transform Data** and update the data source path

---
