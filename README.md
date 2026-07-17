# Predicting Customer Churn for a Subscription Telecom

Portfolio project for **UFCFMM — Business Intelligence and Data Mining** (UWE Bristol, 2025/26 resit).

Ibrahim Puri · 22038398 · BSc (Hons) Computer Science

## What this is

An end-to-end churn analysis on the IBM Telco Customer Churn dataset (7,043 customers): problem framing, EDA, model comparison, and a business + ethics evaluation. The core question — can we identify which customers are about to leave, accurately enough to aim retention offers at them before they go?

Headline results:

- A class-weighted logistic regression beats a decision tree and a 300-tree random forest (0.84 test AUC, 79% recall) — the simplest model wins, and the notebook explains why that's plausible rather than lucky.
- Targeting the top 20% of customers by predicted risk captures ~50% of all churners, roughly 2.5× better than random targeting. Under conservative assumptions that's about $4.70 retained per retention dollar spent.
- The fairness audit finds the model over-flags senior citizens (false-positive rate 0.48 vs 0.25 for non-seniors) — benign in this use case, but the notebook bounds exactly when it would stop being benign.

## Repository contents

| File | What it is |
|---|---|
| `UFCFMM_Churn_Portfolio.ipynb` | The full analysis — narrative, code and outputs |
| `Telco-Customer-Churn.csv` | The dataset ([IBM sample data](https://github.com/IBM/telco-customer-churn-on-icp4d)) |
| `README.md` | This file |

## Running it

Python 3.10+ with `pandas`, `scikit-learn`, `matplotlib` and `seaborn`:

```
pip install pandas scikit-learn matplotlib seaborn
jupyter notebook UFCFMM_Churn_Portfolio.ipynb
```

Everything is seeded (`SEED = 42`), so a full re-run reproduces every figure and number in the notebook. The CSV needs to sit in the same directory as the notebook.

## Notes

Individual submission (group of one). Generative AI (Anthropic Claude) was used in an assistive role for drafting and structuring, in line with the module's permitted-use policy — all analysis was executed, verified and critically evaluated by the author.
