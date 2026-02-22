# A/B Test: Payment Mechanics Experiment

This repository contains a full analytical report of an A/B test evaluating a new payment mechanism.

The experiment compares:
- **Group A** — baseline payment flow (control)
- **Group B** — new payment flow (treatment)

The goal is to determine whether the new payment mechanism should be rolled out to all users.

---

## Experiment Overview

One of the key responsibilities of a product analyst is to correctly design and evaluate experiments.

In this case:
- The treatment group was exposed to a new payment flow.
- The control group retained the original payment flow.
- We analyze revenue impact, statistical significance, and business relevance.

---

## Input Data

The analysis is based on four CSV files:

- `groups.csv` — user assignment to A/B groups  
- `groups_add.csv` — additional users received 2 days later  
- `active_studs.csv` — users active during experiment days  
- `checks.csv` — user payments during experiment days  

All preprocessing, validation, and merging steps are documented in the notebook.

---

## Metrics Analyzed

The following metrics were evaluated:

- **ARPU (Average Revenue Per User)**
- **Median revenue**
- **Conversion rate**
- **ARPPU (Average Revenue Per Paying User)**
- Distribution analysis (skewness, outliers)
- Absolute and relative revenue uplift

Both statistical and economic significance are assessed.

---

## Statistical Approach

Because revenue distributions are typically right-skewed and sample sizes may differ, we apply:

- Normality testing (Shapiro–Wilk)
- Permutation test for p-value estimation
- Bootstrap (percentile method) for confidence intervals
- Holm–Bonferroni correction for multiple comparisons

This approach avoids strong parametric assumptions and provides robust inference.

---

## Key Questions Answered

- Which metrics are relevant and why?
- Are there differences between groups?
- Are the differences statistically significant?
- Are they economically meaningful?
- Should the new payment flow be rolled out?
