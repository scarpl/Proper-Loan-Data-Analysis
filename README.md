# Prosper Loan Data Analysis
## by Luca Scarpantonio

## Dataset

The dataset used for this analysis comes from **Prosper**, a peer-to-peer lending platform.  
It contains loan-level information such as borrower interest rates, credit risk scores, loan amounts, terms, and loan statuses.

- **Number of records:** ~20,000 (sampled from the original dataset)
- **Number of features:** 81 columns (only a subset was used for the analysis)
- **Time range:** 2005–2014 (but loans before 2009 were excluded due to missing `ProsperScore`)

### Data Wrangling
Before starting the exploration, I performed the following steps:
- Filtered loans to keep only those **after 2009** (complete `ProsperScore` coverage).
- Removed rows with `IncomeRange = "Not displayed"` (~5% of data).
- Dropped missing values in key variables: `BorrowerAPR`, `LoanOriginalAmount`, `LoanStatus`.
- Converted `Term` and `ProsperScore` to categorical variables with ordered levels.

This resulted in a clean dataset of ~20k rows suitable for analysis.

---

## Summary of Findings

During the exploratory data analysis, I discovered:

- **BorrowerAPR** is right-skewed, with most values between 10–30%.
- **ProsperScore** is inversely correlated with BorrowerAPR → higher score = lower interest rates.
- **Loan Term** distribution is dominated by 36-month loans, followed by 60-month loans.
- **Loan Amount** increases with longer terms.
- **Loan Status** distribution shows most loans are **Completed**, followed by **Current**, with a smaller share of **Chargedoff** and delinquent loans.
- Borrowers with **lower income ranges** or **unstable employment** tend to have higher APRs.
- Post-2009 data is more reliable, and this choice avoids bias due to missing ProsperScore values.

---

## Key Insights for Presentation

The explanatory analysis focuses on a few key threads to tell a clear story:

1. **Risk-Based Pricing:**  
   BorrowerAPR decreases as ProsperScore increases, demonstrating Prosper's risk-based pricing strategy.

2. **Socio-Economic Factors:**  
   EmploymentStatus and IncomeRange show clear patterns: lower income and unemployment lead to higher APRs.

3. **Loan Term & Performance:**  
   Longer-term loans (60 months) are larger but slightly riskier, with more charged-off loans compared to 36-month loans.

### Design Changes from Part I
- Smoothed the BorrowerAPR histogram with a KDE overlay and annotated mean line.
- Used violin plots to highlight distribution spread by ProsperScore.
- Applied a consistent color palette and larger figure sizes for readability.
- Grouped multiple related plots (APR & Loan Amount vs Term, LoanStatus distribution) into compact visual summaries.