# Prosper Loan Data Exploration  
## by Luca Scarpantonio

---

## Dataset

This project analyzes the **Prosper Loan Dataset**, which contains information on over 110,000 loans facilitated by Prosper Marketplace, including borrower details, loan amounts, interest rates (BorrowerAPR), credit ratings (ProsperScore), and repayment outcomes (LoanStatus).

**Data Wrangling Steps:**
- **Excluded loans issued before 2009** to ensure full availability of `ProsperScore` (introduced that year).
- **Removed rows with missing key fields** (`BorrowerAPR`, `LoanOriginalAmount`, `LoanStatus`).
- **Dropped rows where `IncomeRange` = "Not displayed"** to reduce noise and keep the analysis focused on meaningful borrower segments.

After cleaning, the dataset was ready for univariate, bivariate, and multivariate exploration.

---

## Summary of Findings

### Univariate Exploration
- **BorrowerAPR**: Right-skewed distribution, with most loans between **10% and 30% APR**.  
- **ProsperScore**: Roughly uniform distribution between 4–8, confirming that post-2009 loans have complete scores.  
- **Loan Status**: Completed loans represent the majority, but Chargedoff loans are significant enough to warrant further investigation.  
- **Income Range**: Borrowers are mostly in the $25k–75k range; <5% have "Not displayed" and were removed.  
- **Term**: Loans are primarily 36 months, with smaller fractions at 12 and 60 months.

### Bivariate Exploration
- **ProsperScore vs BorrowerAPR**: Strong negative relationship — higher ProsperScore leads to lower APR.  
- **Loan Amount vs ProsperScore**: Higher ProsperScore borrowers tend to obtain larger loans.  
- **Employment Status vs Loan Status**: Part-time borrowers have the highest rate of default/charged-off loans.

### Multivariate Exploration
- **APR, ProsperScore, Loan Amount** combined show a clear trend: low-score borrowers face higher APRs and generally receive smaller loans.  
- **Income Range vs Employment Status vs Default Rate**: Part-time borrowers and those with lower income ranges have a higher default probability, confirming socio-economic risk factors.

---

## Key Insights for Presentation

The explanatory slide deck focuses on three main insights:

1. **BorrowerAPR Distribution**  
   Most loans cluster between 10–30% APR, motivating the need to explore what drives rate variability.

2. **ProsperScore and APR Relationship**  
   Clear negative correlation: higher ProsperScore (better creditworthiness) leads to lower interest rates.

3. **Loan Status by Employment Status**  
   Part-time borrowers show the highest proportion of defaulted (Chargedoff) loans, indicating that employment stability is a strong predictor of loan performance.

Each visualization in the slide deck is polished, with titles, labeled axes, legends, and clear color encodings. Together, these insights provide a coherent narrative on borrower risk and credit decision-making.

---

## Files in This Repository

- `Part_I_exploration_template.ipynb` – Full exploratory data analysis, including univariate, bivariate, and multivariate plots with commentary.
- `Part_II_slide_deck.ipynb` – Explanatory analysis slide deck summarizing key insights with polished visualizations.
- `README.md` – This file, summarizing the project, findings, and selected insights for presentation.

---

## Dependencies

- Python 3.x  
- Pandas, NumPy, Matplotlib, Seaborn  
- Jupyter Notebook or VS Code with Jupyter extension  

---