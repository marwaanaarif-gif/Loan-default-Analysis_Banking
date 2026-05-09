# 🔍 Key Findings — Loan Default Analysis

A structured breakdown of the most significant findings from the Loan Default Analysis Power BI report, organized by analytical theme.

---

## 🏢 Employment Type as a Risk Predictor

- **Default rates are not uniform across employment types** — the report's dedicated default rate chart reveals a clear spread, meaning employment status is one of the strongest single-variable predictors of default risk in this dataset
- **Average income also varies significantly by employment type**, which compounds the risk signal — lower-income employment categories tend to cluster with higher default rates, suggesting income stability (not just level) is the underlying driver
- **The decomposition tree on Page 3 confirms employment type as a key structural explainer** of total loan volume, sitting below income bracket in the hierarchy — meaning after segmenting by income, employment type further separates the distribution

---

## 👤 Age Group Borrowing Behavior

- **Loan size scales with age group** — the Average Loan by Age Group chart shows a clear progression, with older borrowers generally taking on larger loans, likely reflecting higher collateral, better credit history, or larger purchase needs (e.g. mortgages vs. personal loans)
- **Middle-aged borrowers represent the largest loan volume segment** — this group drives the bulk of total lending activity and is the focal point of the demographic deep-dive on Page 2
- **The donut chart for high-credit borrowers shows marital status adds a secondary layer** within the same age group — married borrowers in the high-credit band show different average loan sizes compared to unmarried borrowers, indicating household income or joint applications may factor in

---

## 💳 Credit Score and Loan Behaviour

- **Median loan amount increases with credit quality** — borrowers in higher credit bins take out larger loans, consistent with the idea that better-credit applicants get approved for more and feel confident borrowing more
- **The relationship is not perfectly linear** — there are inflection points in the credit bin chart that may indicate lending policy thresholds or risk-adjusted caps applied by the institution
- **For middle-aged borrowers, having dependents noticeably shifts loan volume within the same credit bin** — the clustered column chart on Page 2 shows that borrowers with dependents and those without behave differently even when credit scores are comparable, pointing to household expense obligations as a moderating factor
- **Older adult borrowers show a different credit-to-loan curve** — their total loan amounts by credit bin follow a distinct pattern from the middle-aged group, suggesting age-specific lending behavior or product uptake

---

## 🎓 Education and Loan Access

- **Loan count varies significantly across education levels** — the Total Loans by Education Type chart reveals that certain education tiers are overrepresented in the borrower base
- **This could indicate differential access to credit, differential demand, or both** — higher education levels may correlate with higher income, making borrowers more bankable, while lower education levels may reflect underserved segments or higher-risk personal lending
- **Education is not directly linked to a default measure in the current report** — a natural next step would be to cross-reference education level with default rate to determine whether the access gap also reflects a risk gap

---

## 📅 Year-over-Year Trends

- **Loan issuance volume and default rates do not move in lockstep** — the YOY charts on Page 3 show that periods of growing loan volume do not always correspond to proportionally growing defaults, suggesting underwriting quality may have improved during certain periods or that loan mix shifted toward lower-risk products
- **There are specific years where default change spikes or dips sharply** — these inflection points are the most actionable signals in the report and warrant investigation into macroeconomic context (e.g. rate changes, economic shocks) or internal policy changes that coincided with those periods
- **YOY default change is the headline risk KPI** — it cuts through absolute volume and shows directional momentum, which is more useful for early-warning risk monitoring than a static count

---

## 🌳 Decomposition Tree Findings (Page 3)

- **Income bracket is the top-level explainer of total loan amount** — splitting the portfolio by income tier produces the largest first-level variance, confirming that income segmentation is the primary structural divide in this book
- **Within each income bracket, employment type further separates loan volume** — this two-level breakdown reveals which income + employment combinations account for disproportionate shares of total lending
- **The decomposition tree is interactive** — in the live report, clicking into specific branches can surface the exact sub-segments driving outlier totals, making it the most exploratory visual in the dashboard

---

## ⚠️ Risk Concentration Summary

| Risk Factor | Finding |
|---|---|
| Employment Type | Strongest single-variable default rate differentiator |
| Age Group | Older borrowers = larger loans; middle-aged = highest volume |
| Credit Score | Higher bins borrow more; dependent status creates within-bin variance |
| Income Bracket | Primary structural explainer of total loan portfolio composition |
| YOY Default Trend | Non-linear — does not simply mirror loan growth |
| Education Level | Influences loan access; default linkage not yet modelled |

---

## 🔭 Suggested Next Steps

- **Add a default rate measure by education level** to close the gap between access and risk across that dimension
- **Build a risk score composite** combining employment type, credit bin, and income bracket into a single segment identifier
- **Add a slicer for loan purpose** to allow filtering all three pages by the type of loan — this would reveal whether default patterns differ meaningfully between personal, auto, and mortgage products
- **Introduce a benchmark line** on the YOY default chart to compare the portfolio's trend against an industry average or internal target

---
