# Hypothesis Testing in Python

This project demonstrates how to apply **parametric** and **non-parametric hypothesis tests** using a real-world **Car Dataset**.  
It covers tests like t-test, ANOVA, Chi-Square, Mann–Whitney, and Kruskal–Wallis with Python implementations, visualizations, and short interpretations.

---

## 📊 Dataset Overview
The dataset contains information on **428 cars**, including attributes such as:
- Make, Model, Type, Origin, DriveTrain  
- Engine Size, Cylinders, Horsepower, MPG (City & Highway)  
- MSRP, Invoice, Weight, Wheelbase, Length  

Used to explore relationships between numerical and categorical variables.

---

## 🧠 Key Objectives
- Perform **parametric** and **non-parametric hypothesis testing**
- Compare mean differences across groups (Origin, Type, DriveTrain)
- Check **normality** and **variance equality**
- Visualize and interpret results for practical decision-making

---

## ⚙️ Tests Included

| Test | Use Case | Example Hypothesis | Decision Basis |
|------|-----------|--------------------|----------------|
| One-Sample t-test | Compare mean to known value | Horsepower ≠ 200 | Based on p-value |
| Independent t-test | Compare two origins | USA vs Europe MSRP | Based on p-value |
| ANOVA | Compare 3+ groups | Sedan vs SUV vs Sports | Based on p-value |
| Mann–Whitney | Non-parametric 2 groups | USA vs Europe | Based on p-value |
| Kruskal–Wallis | Non-parametric ANOVA | Car Types | Based on p-value |
| Chi-Square | Categorical relationship | Origin vs DriveTrain | Based on p-value |

---

## 📈 Example Code

```python
from scipy.stats import ttest_ind, f_oneway, chi2_contingency

# Example: Compare MSRP by Origin (Independent t-test)
usa = df[df['Origin'] == 'USA']['MSRP']
europe = df[df['Origin'] == 'Europe']['MSRP']

t_stat, p_val = ttest_ind(usa, europe)
print("T-statistic:", t_stat, "P-value:", p_val)
if p_val < 0.05:
    print("Reject H₀ → Significant difference in average price.")
else:
    print("Fail to reject H₀ → No significant difference.")


# Author

- Awais Manzoor
- Data Analyst | Python & SQL Enthusiast
