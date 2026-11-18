# Module 7 and Module 9 data — Meridian Commerce customer purchases

`customer_purchases.csv` is a **synthetic** table of **2,500 customers** of the fictional online marketplace Meridian Commerce, one row per customer's latest visit, with eight things known the moment the visit ends and one thing to predict: whether the customer placed an order in the 30 days that followed. No row describes a real person. Released **CC0** (public domain).

| Column | Meaning | Range |
|---|---|---|
| `age` | The customer's age in years | 18 to 75 (166 customers are recorded at 18, the lowest value) |
| `income` | Annual household income, dollars | 20,000 to 200,000 (415 customers are recorded at 20,000, the lowest value) |
| `time_on_site` | Minutes spent on the site during the latest visit | 0.5 to 30.0 (270 customers are recorded at 0.5, the lowest value) |
| `pages_viewed` | Pages viewed during the latest visit | 1 to 19 |
| `previous_purchases` | Orders the customer placed before the latest visit | 0 to 9 |
| `days_since_last_visit` | Days between the latest visit and the one before it | 0.0 to 90.0 |
| `email_opens` | Marketing emails opened in the last 30 days | 0 to 13 |
| `mobile_user` | 1 if the customer mostly shops on a phone, 0 if not | 0 or 1 |
| `purchased` | **The target.** 1 if the customer placed an order in the 30 days after the visit, 0 if not | 0 or 1 |

- **Rows and columns:** 2,500 × 9, no missing values.
- **Class balance:** 1,377 customers ordered (55.1%) and 1,123 did not (44.9%).
- **Used by:** the Module 7 lecture notebook (neural networks), the Module 9 lecture notebook (PyTorch) and Assignment 3.
- **How it was made:** simulated once, with a fixed random seed. The file never changes during the term.

Load it by URL:

```python
import pandas as pd
url = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data/module09/customer_purchases.csv"
df = pd.read_csv(url)
```

---

# Module 9 data — the PyTorch demonstrations

Four small **synthetic** tables with no story: two features, `x1` and `x2`, and an answer, `y`, 500 rows each. Each is used by one of Module 9's demonstration notebooks, which learn from the first 400 rows and hold back the last 100. The rows are in random order. Each file was made from a simple rule plus chance, and the notebooks state the rule, so that what a model learns can be checked against it. Released **CC0** (public domain).

| File | `x1`, `x2` | `y` | The rule | Used by |
|---|---|---|---|---|
| `demo_linear.csv` | numbers between −1 and 1 | a number | y = 3 × x1 − 2 × x2 + 1, plus a little random noise | Notebook 1: linear regression |
| `demo_logistic.csv` | numbers mostly between −3 and 3 | 0 or 1 | score = 2 × x1 − x2; the higher the score, the more often y is 1 (the probability of a 1 is the sigmoid of the score) | Notebook 2: logistic regression |
| `demo_network.csv` | numbers mostly between −3 and 3 | 0 or 1 | y is nearly always 1 when x1 and x2 are within 1 of each other, and nearly always 0 when they are further apart | Notebook 3: a small neural network |
| `demo_three_classes.csv` | numbers mostly between −3 and 3 | 0, 1 or 2 | each class is a cloud of points around its own centre: class 0 around (0, 1.2), class 1 around (−1.2, −0.8), class 2 around (1.2, −0.8). The clouds overlap | Notebook 4: three classes, mini-batches, early stopping, dropout |

```python
import pandas as pd
url = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data/module09/demo_linear.csv"
df = pd.read_csv(url)
```

# Module 9 data — Tamarack Plastics (an earlier version of the demonstrations)

*The three tables below are not used by the current Module 9 notebooks, which read the `demo_` files above.*


Three small **synthetic** tables about the fictional company Tamarack Plastics, which molds plastic parts to order. Each is used by one of Module 9's demonstration notebooks. No row describes a real job, customer or part. Released **CC0** (public domain).

## `tamarack_job_costs.csv`: what will this job cost?

| Column | Meaning | Range |
|---|---|---|
| `material_kg` | Plastic planned for the job, in kilograms | 20 to 400 |
| `machine_hours` | Hours planned on a molding machine | 2.0 to 40.0 |
| `setup_changes` | Times the plan sets the machine up again during the job (a new mold or a new color) | 0 to 6 |
| `rush_order` | 1 if the customer paid for a rush, 0 if not | 0 or 1 |
| `job_cost_thousands` | **The target.** What the job turned out to cost Tamarack, in thousands of dollars (2.844 means 2,844 dollars) | 0.684 to 6.393 |

- **Rows and columns:** 1,000 × 5, no missing values. One row per finished job.
- **Used by:** `Module09-pytorch-1-linear-regression.ipynb` (a linear regression in PyTorch).

## `tamarack_quotes.csv`: will the customer accept the quote?

| Column | Meaning | Range |
|---|---|---|
| `price_vs_market_pct` | How far the quoted price is above the going market price, in percent (negative: below it) | -15.0 to 25.0 |
| `lead_time_days` | Days from the order to delivery, as promised in the quote | 5 to 45 |
| `past_orders` | Orders this customer has placed with Tamarack before | 0 to 9 |
| `existing_tooling` | 1 if Tamarack already holds a mold for this customer, 0 if not | 0 or 1 |
| `accepted` | **The target.** 1 if the customer accepted the quote, 0 if not | 0 or 1 |

- **Rows and columns:** 1,000 × 5, no missing values. One row per quote sent.
- **Class balance:** 591 quotes were accepted (59.1%) and 409 were not.
- **Used by:** `Module09-pytorch-2-logistic-regression.ipynb` (a logistic regression in PyTorch).

## `tamarack_inspections.csv`: will this batch of parts pass inspection?

| Column | Meaning | Range |
|---|---|---|
| `melt_temp_c` | Temperature of the melted plastic, degrees Celsius | 200.0 to 260.0 |
| `hold_pressure_bar` | Pressure holding the plastic in the mold, in bar | 380 to 920 |
| `cooling_time_s` | Seconds the part cools before the mold opens | 8.0 to 30.0 |
| `regrind_pct` | Share of recycled plastic in the mix, in percent | 0 to 30 |
| `passed` | **The target.** 1 if the batch passed inspection, 0 if it failed | 0 or 1 |

- **Rows and columns:** 2,000 × 5, no missing values. One row per batch of parts.
- **Class balance:** 762 batches passed (38.1%) and 1,238 failed.
- **Used by:** `Module09-pytorch-3-neural-network.ipynb` (a neural network in PyTorch).

**How they were made:** simulated once, with fixed random seeds. The files never change during the term.

Load one by URL:

```python
import pandas as pd
url = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data/module09/tamarack_job_costs.csv"
df = pd.read_csv(url)
```
