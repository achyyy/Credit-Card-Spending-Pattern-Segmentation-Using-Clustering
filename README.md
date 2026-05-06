# Credit Card Spending Pattern Segmentation

## Project Overview
This repository contains an analysis for customer segmentation based on credit-card spending behavior. The aim is to identify actionable customer archetypes using clustering (KMeans) and provide summary outputs for business insights.

What I implemented:
- Exploratory Data Analysis (distributions, boxplots, correlation heatmap)
- Simplified pre-clustering visualization (utilization histogram with 0.8 risk threshold)
- Data cleaning (missing values handled with medians, duplicate removal)
- Robust scaling (RobustScaler) to mitigate outlier effects
- Elbow method (K=1–10) and KMeans clustering (K=4 selected for interpretability)
- PCA (2 components) for cluster visualization with labeled archetypes
- Cluster profiling and summary statistics

## Files
- `creditcard.ipynb` — Clean analysis notebook (run cells top → bottom)
- `dataset/CC GENERAL.csv` — Original dataset (not modified)
- `clustered_customers.csv` — Dataset with `Cluster` column appended
- `eda/` — Generated plots (distributions, correlation, elbow, PCA, cluster characteristics, utilization, etc.)

## Cluster Archetypes (added to PCA viz)
- `Convenience Users` — Majority; low balance and moderate purchases
- `Cash Advance Heavy` — High cash-advance behavior and balances
- `Premium Spenders` — High purchase volume and payments; good payment consistency
- `High-Risk` — High balances, cash advances, low full-payment rates

## How to run (recommended)
1. Create & activate a Python virtual environment (Windows PowerShell example):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. Install required packages:

```powershell
pip install pandas numpy matplotlib seaborn scikit-learn
```
3. Open `creditcard.ipynb` in Jupyter or VS Code and run cells from top to bottom. The notebook will:
   - produce plots in `eda/`
   - save `dataset/clustered_customers.csv` and `dataset/cluster_summary.csv`

Note: The notebook keeps `spending_vs_payment.png` as an appendix visual and uses `utilization.png` as the primary pre-clustering chart.

## Deliverables 
- Insight report (PDF): Export a short PDF summarizing findings, cluster interpretations, and recommended actions for each archetype.
- Dashboard link or screenshots: Create a dashboard (Power BI / Tableau / Streamlit / Dash) summarizing cluster counts, key metrics per cluster, and PCA visualization. Save screenshots to include with submission.
- Clean analysis notebook: `creditcard.ipynb` (this notebook is organized; run it to reproduce outputs)

 ## Insights
- Data Quality: Median imputation and duplicate removal produce a clean, analysis-ready dataset.
- High Utilization Risk: ~20% of customers have utilization > 0.8, indicating repayment pressure and elevated credit risk.
- Four Actionable Archetypes: Convenience Users: low balances; Cash Advance Heavy: high cash-advance usage and balances; Premium Spenders: high purchases with consistent payments; High-Risk: high balances, low payment rates.
- Priority Segments: Focus risk-mitigation on High-Risk and Cash Advance Heavy clusters to reduce potential defaults.
- Commercial Opportunities: Premium Spenders are candidates for loyalty/upsell programs and credit-product cross-sell.
- Operational Recommendations: Implement targeted outreach (repayment assistance, tailored credit limits, preventive monitoring) for at-risk clusters.
- Model Notes: K=4 was chosen for interpretability; the elbow plot showed no sharp knee—validate with Silhouette/Davies–Bouldin scores before production.

 ## BI Dashboards

<img width="949" height="533" alt="Screenshot 2026-05-06 174422" src="https://github.com/user-attachments/assets/990d5dc6-843a-4cd2-8d53-1dea4f04f4ae" />
<img width="949" height="534" alt="Screenshot 2026-05-06 174400" src="https://github.com/user-attachments/assets/fa2b8c55-7fa9-422b-83a4-b5fdb8674c4f" />
<img width="948" height="533" alt="Screenshot 2026-05-06 174324" src="https://github.com/user-attachments/assets/bf5fccfc-9498-4e6d-b0e3-83d3ff70fe22" />
