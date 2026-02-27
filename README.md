# B2B Sales Pipeline Analysis

**What drives revenue outcomes across 8,800 B2B CRM deals**

![Python](https://img.shields.io/badge/Python-3.14-blue)
![pandas](https://img.shields.io/badge/pandas-2.x-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dv-data-analyst/b2b-sales-pipeline-analysis/blob/main/notebook.ipynb)

---

## Quick Navigation

- [notebook.ipynb](./notebook.ipynb) — Full analysis
- [data/raw/README.md](./data/raw/README.md) — Data dictionary, source, and license
- [assets/b2b_pipeline_case_study.pdf](./assets/b2b_pipeline_case_study.pdf) — LinkedIn carousel (PDF)

---

## Project Summary

This project analyzes 8,800 B2B sales opportunities from a CRM dataset to identify what drives revenue outcomes across products, reps, and time. Using Python and pandas, I tested four hypotheses across product mix, rep performance, and seasonal loss patterns. Key finding: win rate and revenue are uncorrelated at the rep level (r = -0.09), while deal volume strongly correlates with revenue (r = 0.81, r² = 0.66). All outputs were cross-validated in Google Sheets. Recommendations target product focus, KPI design, and timing of pipeline investment.

---

## Key Findings

| # | Finding | Implication |
|---|---------|-------------|
| 01 | Top 3 products account for 83% of **estimated** lost revenue ($5.95M total): GTXPro $2.0M, MG Advanced $1.46M, GTX Plus Pro $1.46M *(values rounded)*. | Focus closing and loss-reduction efforts on these three SKUs. |
| 02 | GTX Basic drives 22% of won deals but only 5% of revenue. GTXPro drives 17% of won deals but 35% of revenue. | Shift effort toward high-value SKUs, starting with GTXPro. |
| 03 | Win rate and revenue are uncorrelated at the rep level (r = -0.09). Deal volume strongly correlates with revenue (r = 0.81, r² = 0.66). | Evaluate reps on revenue generated, not win rate alone. |
| 04 | Loss rate follows a predictable alternating monthly pattern across the full 15-month window. Low-loss months: March, June, September, December. | Increase pipeline investment 6–8 weeks before low-loss months. |

---

## Definitions

| Metric | Definition |
|--------|------------|
| Win Rate | Won / (Won + Lost). Open opportunities excluded from all calculations. |
| Loss Rate | Lost / (Won + Lost) by time period. Open opportunities excluded. |
| Lost Revenue (estimated) | Sum of `sales_price` for Lost opportunities. Proxy — assumes 1 unit per opportunity. |
| Deal Volume | Count of Won opportunities per sales rep. |
| Deal Cycle Length | `close_date` minus `engage_date`. Calculated on Won/Lost only. Won deals median: 57 days. |

---

## Dataset

| Field | Value |
|-------|-------|
| Source | Maven Analytics — CRM Sales Opportunities (public dataset) |
| URL | [https://mavenanalytics.io/data-playground/crm-sales-opportunities](https://mavenanalytics.io/data-playground/crm-sales-opportunities) |
| Original source | data.world |
| Records | 8,800 opportunities, Oct 2016 to Dec 2017 (15 months) |
| Key fields | deal_stage, product, sales_agent, close_value, engage_date, close_date |
| License | Public Domain (per dataset page) |
| Downloaded | Feb 2026 |
| Industry benchmark | Average B2B win rate 21% — HubSpot 2024 Sales Trends Report ([PDF](https://www.hubspot.com/hubfs/HubSpots%202024%20Sales%20Trends%20Report.pdf)) |

> **Data quality note:** Product names differ between `sales_pipeline.csv` ("GTXPro") and `products.csv` ("GTX Pro"). This inconsistency is handled in the notebook via a normalized join key. Without this fix, GTXPro ($2.0M estimated lost revenue) would be excluded from product-level analysis. See Section 1 of the notebook for details.

---

## How to Run

**Option A: Colab (recommended — no setup required)**

Click the **Open in Colab** badge above. The notebook includes a setup cell that clones the repository automatically so all data files are available.

**Option B: Run locally**

```bash
git clone https://github.com/dv-data-analyst/b2b-sales-pipeline-analysis
cd b2b-sales-pipeline-analysis
pip install -r requirements.txt
jupyter notebook notebook.ipynb
```

---

## Tools

`Python 3.14` · `pandas` · `numpy` · `matplotlib` · `Jupyter Notebook` · `Google Sheets` (cross-validation)

---

## Artifacts

- LinkedIn carousel: [`assets/b2b_pipeline_case_study.pdf`](./assets/b2b_pipeline_case_study.pdf)

---

## License and Reproducibility

Code: MIT License — see [LICENSE](./LICENSE).  
Dataset: Public Domain (per source) — see [data/raw/README.md](./data/raw/README.md).  
Full reproducible notebook available in this repository and linked from the LinkedIn carousel.

---

*Dmytro Vasylenko · Marketing Data Analyst · February 2026*  
*[linkedin.com/in/dv-data-analyst](https://linkedin.com/in/dv-data-analyst)*
