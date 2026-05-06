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
- `cluster_summary.csv` — Aggregated mean metrics per cluster
- `eda/` — Generated plots (distributions, correlation, elbow, PCA, cluster heatmap, utilization, etc.)

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

(If you prefer, create a `requirements.txt` from your environment and install that.)

3. Open `creditcard.ipynb` in Jupyter or VS Code and run cells from top to bottom. The notebook will:
   - produce plots in `eda/`
   - save `dataset/clustered_customers.csv` and `dataset/cluster_summary.csv`

Note: The notebook keeps `spending_vs_payment.png` as an appendix visual and uses `utilization.png` as the primary pre-clustering chart.

## Deliverables (internship requirements)
- Insight report (PDF): Export a short PDF summarizing findings, cluster interpretations, and recommended actions for each archetype.
- Dashboard link or screenshots: Create a dashboard (Power BI / Tableau / Streamlit / Dash) summarizing cluster counts, key metrics per cluster, and PCA visualization. Save screenshots to include with submission.
- Clean analysis notebook: `creditcard.ipynb` (this notebook is organized; run it to reproduce outputs)

## Suggested next steps (optional)
- Create a short one-page slide deck or PDF with top 3–5 insights and recommended actions per cluster.
- Build a simple Streamlit dashboard to let mentors interactively explore clusters.
- Compute additional validation metrics (Silhouette score, Davies–Bouldin) if requested by mentors.

## Contact / Notes
If you want, I can:
- Draft the insight report PDF from notebook outputs and cluster summaries.
- Generate dashboard screenshots or scaffold a Streamlit dashboard.

---
Generated: May 5, 2026
