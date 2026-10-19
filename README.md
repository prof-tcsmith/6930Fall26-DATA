# 6930 Course Data — Fall 2026

Public datasets for **6930 Applied Machine Learning for Business**, Fall 2026 (University of
South Florida, Dr. Tim Smith).

These files are loaded directly by the lecture, lab and assignment notebooks in the course.
Notebooks reference them by raw GitHub URL, so they work in Google Colab with no download step:

```python
import pandas as pd

DATA_URL = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data"
df = pd.read_csv(f"{DATA_URL}/module02/sales_transactions.csv")
```

**All data in this repository is synthetic or openly licensed.** Companies, people,
transactions and measurements are fictional and were generated for teaching. Any resemblance to
real businesses or persons is coincidental. Where a dataset is a sample of a public one, its
folder says so and names the licence.

## Layout

```text
data/
├── module01/   Course Introduction — Bay Harbor Coffee daily sales
├── module02/   Data Preparation — Horizon Coffee transactions, customers, orders
├── module03/   Linear Regression — assignment/: Pelican Row Growers tray trial;
│               practice/: Ridgeline Facilities building energy
├── module04/   Logistic Regression — churn, loan default, employee attrition
├── module05/   KNN and SVM — insurance churn, trial conversions, SecureBank card transactions (4,000 rows, 4.7% fraud)
├── module06/   Decision Trees & Ensemble Methods — lendsafe_applications.csv (the lecture notebooks);
│               insurance_claims.csv (Pinnacle Insurance Group, Assignment 2)
├── module09/   Neural Networks (Module 8) and PyTorch (Module 9) — customer_purchases.csv: 2,500 simulated Meridian Commerce
│               customers, eight features and a purchase flag
├── module10/   CNN — fashion_mnist_small.npz: a stratified Fashion-MNIST sample (12,000 train, 2,000 test)
├── module11/   Text and RNN — support_tickets.csv: 3,000 synthetic support tickets in five queues
│   (modules 09, 10 and 11 are added during the term:
│    09 Meridian Commerce purchases, 10 catalog images, 11 support tickets)

```

Folder numbers are **6930 module numbers**. Module 7 has no folder: its notebook reuses
`module04/customer_churn.csv`. Module 8 has none either: its notebook uses the customers of
`module09/customer_purchases.csv`, the file Module 9 and Assignment 3 go on to use. This repository holds **data only**: the scripts that generated a
dataset are not published. (Module 3's lecture
demonstrations also generate their data inline, on purpose: seeing the hidden relationship is
the lesson. Its lab and practice data live here.)

## The final project

The final project's scenarios and data are published separately, when the project opens.

## Stability guarantee

**Files are never moved, renamed, or altered once the semester starts.** Student notebooks
depend on these URLs resolving for the whole term. Corrections, if ever required, are
published as a new file alongside the original.

## Provenance

Modules 1–6 data come from the ISM4543 Fall 2026 course data repository
(`prof-tcsmith/4543Fall26-DATA`), renumbered: its `week01`, `week03`, `week04`, `week05`,
`week06` + `week07`, and `week09` folders are `module01`, `module02`, `module03`, `module04`,
`module05` and `module06` here.

---

© Dr. Tim Smith, 2026. Provided for educational use in 6930.
