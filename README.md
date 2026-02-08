
# 📈 Growth Analytics & A/B Testing

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-1.6-orange?logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Statsmodels](https://img.shields.io/badge/Statsmodels-0.19-green?logo=python&logoColor=white)](https://www.statsmodels.org/)

---

## 📌 Project Overview
This project demonstrates **growth analytics and A/B testing**, focusing on **decision-making metrics** rather than just charts. It simulates **real-world scenarios** used in Big Tech, SaaS, e-commerce, and fintech, showcasing **mid-level analyst thinking**.

**Goal:** Identify which variant drives higher conversion and revenue, with **statistical confidence**, to inform business decisions.

---

## 📊 Dataset
- **File:** `AB_Test.csv`
- **Type:** Synthetic, portfolio-safe, realistic

| Column | Description |
| :--- | :--- |
| **user_id** | Unique identifier for each user |
| **group** | Control vs Variant |
| **converted** | Binary conversion flag (0/1) |
| **revenue** | Revenue per user |

---

## ⏱ Step-by-Step Analysis (Python)

### Step 1: Load Data
```python
import pandas as pd

df = pd.read_csv("AB_Test.csv")
df.head()

```

### Step 2: Basic Sanity Checks

```python
df.info()
df.groupby("group")["converted"].mean()

```

*Checked data quality, missing values, and balanced sample sizes before analysis.*

### Step 3: Conversion Rate Analysis

```python
conversion = df.groupby("group")["converted"].mean() * 100
print(conversion)

```

**Insight:** Variant shows a lift in conversion compared to Control.

### Step 4: Revenue Impact

```python
revenue = df.groupby("group")["revenue"].mean()
print(revenue)

```

**Business Framing:** Variant not only improved conversion but also increased average revenue per user.

### Step 5: Statistical Significance

```python
from statsmodels.stats.proportion import proportions_ztest

control = df[df["group"]=="Control"]["converted"]
variant = df[df["group"]=="Variant"]["converted"]

count = [variant.sum(), control.sum()]
nobs = [len(variant), len(control)]

stat, pval = proportions_ztest(count, nobs)
print(f"P-Value: {pval}")

```

*Demonstrates understanding of hypothesis testing, not just charts.*

---

## 🏁 Conclusion & Recommendations

The Variant outperformed Control in both conversion rate and revenue. With a **statistically significant p-value (<0.05)**, the experiment supports rolling out the Variant to all users.

### 📊 Optional Power BI Dashboard

* **KPI Cards:** Conversion Rate, Revenue per User, Lift %
* **Visuals:** Bar chart comparing Control vs Variant visually.

---

## 💡 Business Use Cases

* **Optimize product experiments** with actionable insights.
* **Make data-driven decisions** for revenue and growth.
* **Test hypotheses** and validate strategies before rollout.

---

## 👤 Author

**Olufemi Olamoyegun** Data Analyst | Power BI | SQL | Workforce & Business Analytics

🔗 [LinkedIn](https://www.linkedin.com/in/olufemi-olamoyegun) | 📂 [GitHub](https://github.com/olufemiolamoyegun)









