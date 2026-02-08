# 📈 Growth Analytics & A/B Testing

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)]
[![Pandas](https://img.shields.io/badge/Pandas-1.6-orange?logo=pandas&logoColor=white)]
[![Statsmodels](https://img.shields.io/badge/Statsmodels-0.19-green?logo=python&logoColor=white)]

---

## 📌 Project Overview
This project demonstrates **growth analytics and A/B testing**, focusing on **decision-making metrics** rather than just charts.  
It simulates **real-world scenarios used in Big Tech, SaaS, e-commerce, and fintech**, showcasing **mid-level analyst thinking**.

**Goal:** Identify which variant drives higher conversion and revenue, with **statistical confidence**, to inform business decisions.

---

## 📊 Dataset
- **File:** `AB_Test.csv`  
- **Type:** Synthetic, portfolio-safe, realistic  
- **Columns:**  

| Column     | Description                          |
|-----------|--------------------------------------|
| user_id   | Unique identifier for each user      |
| group     | Control vs Variant                   |
| converted | Binary conversion flag (0/1)         |
| revenue   | Revenue per user                      |

---

## ⏱ Step-by-Step Analysis (Python)

### Step 1: Load Data
```python
import pandas as pd

df = pd.read_csv("AB_Test.csv")
df.head()
Step 2: Basic Sanity Checks
df.info()
df.groupby("group")["converted"].mean()
Checked data quality, missing values, and balanced sample sizes before analysis.

Step 3: Conversion Rate Analysis
conversion = df.groupby("group")["converted"].mean() * 100
conversion
Insight Example: Variant shows a +X% lift in conversion compared to Control.

Step 4: Revenue Impact
revenue = df.groupby("group")["revenue"].mean()
revenue
Variant not only improved conversion but also increased average revenue per user.

Step 5: Statistical Significance
from statsmodels.stats.proportion import proportions_ztest

control = df[df["group"]=="Control"]["converted"]
variant = df[df["group"]=="Variant"]["converted"]

count = [variant.sum(), control.sum()]
nobs = [len(variant), len(control)]

stat, pval = proportions_ztest(count, nobs)
pval
Demonstrates understanding of hypothesis testing, not just charts.

Step 6: Conclusion
The Variant outperformed Control in both conversion rate and revenue. With a statistically significant p-value (<0.05), the experiment supports rolling out the Variant to all users.

Step 7: Optional Power BI Dashboard
Upload AB_Test.csv

Create KPI cards:

Conversion Rate

Revenue per User

Lift %

Add a bar chart comparing Control vs Variant visually

💡 Business Use Cases

Optimize product experiments with actionable insights

Make data-driven decisions for revenue and growth

Test hypotheses and validate strategies before rollout

👤 Author
Olufemi Olamoyegun
Data Analyst | Python | Growth & Product Analytics

[LinkedIn](https://www.linkedin.com/in/olufemi-olamoyegun) | [GitHub](https://github.com/olufemiolamoyegun)

---

[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=olufemiolamoyegun&layout=compact)](https://github.com/olufemiolamoyegun)
[![GitHub Stats](https://github-readme-stats.vercel.app/api?username=olufemiolamoyegun&show_icons=true)](https://github.com/olufemiolamoyegun)



📊 GitHub Stats

