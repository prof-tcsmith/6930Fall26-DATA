# Module 8 and Module 9 data — Meridian Commerce customer purchases

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
- **Used by:** the Module 8 lecture notebook (neural networks), the Module 9 lecture notebook (PyTorch) and Assignment 3.
- **How it was made:** simulated once, with a fixed random seed. The file never changes during the term.

Load it by URL:

```python
import pandas as pd
url = "https://raw.githubusercontent.com/prof-tcsmith/6930Fall26-DATA/main/data/module09/customer_purchases.csv"
df = pd.read_csv(url)
```
