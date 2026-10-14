# 🧪 Automated A/B Testing Framework & Statistical Significance Analysis

An end-to-end Python analytics framework built to evaluate multiple A/B experiments on e-commerce funnel metrics (payment info addition, shipping setup, checkout initiation, and account creation). The project automates multi-metric conversion rate calculation, statistical z-testing for proportions, and interactive visualization in Tableau.

---

## 📌 Project Overview & Objectives
The primary objective was to evaluate product and user-interface experiments across key conversion funnel stages. By automating data aggregation and hypothesis testing, the framework calculates conversion rate changes between control and test groups and determines statistical significance ($p < 0.05$) using Z-tests for proportions.

---

## 🛠️ Tech Stack & Skills
* **Python Stack:** Pandas, NumPy, Statsmodels (`statsmodels.stats.proportion.proportions_ztest`)
* **Statistical Methods:** Z-test for Proportions, Hypothesis Testing ($p$-value evaluation, $Z$-score calculation, Statistical Significance thresholding)
* **Data Processing:** Automated iterative loop processing across metrics and test variants
* **Business Intelligence:** Tableau Public (Interactive Experiment Dashboard)

---

## 📊 Analytical & Pipeline Workflow

1. **Dataset Loading & Preprocessing:**
   * Ingested query results containing event logs across multiple A/B test groups (`control_group = 2`, `test_group = 1`).

2. **Automated Multi-Metric Evaluation Loop:**
   * Dynamically processed key conversion metrics:
     * `add_payment_info / session`
     * `add_shipping_info / session`
     * `begin_checkout / session`
     * `new_accounts / session`
   * Calculated baseline conversion rates ($CR_{control}$ vs $CR_{test}$) and relative metric lift/change (%).

3. **Statistical Hypothesis Testing Engine:**
   * Executed Two-Sample Z-Tests for Proportions across every metric and experiment ID.
   * Derived **Z-statistics** and **$p$-values** with built-in zero-division safety and exception handling.
   * Flagged statistically significant outcomes ($p < 0.05$) to separate true business impact from random noise.

4. **BI Dashboard Integration:**
   * Exported structured test results to CSV for clear reporting and interactive filtering in Tableau.

---

## 💡 Key Findings & Experiment Outcomes

* 📉 **Test Variant 1 (Checkout & Funnel Modifications):**
  * **Shipping & Checkout Drop-off:** Showing a statistically significant drop ($p = 0.0219$ and $p = 0.0239$) in conversion rates for `add_shipping_info` and `begin_checkout` stages. **Recommendation:** Roll back UI changes in Test 1 as they created friction in the purchase funnel.
* 📈 **Test Variant 4 (Registration Flow):**
  * **Account Creation Lift:** Generated a statistically significant increase in new account registrations ($p = 0.0175$, $Z = 2.375$). **Recommendation:** Adopt Variant 4 for onboarding optimization.
* ⚖️ **Inconclusive Experiments:** Metrics with $p \ge 0.05$ (e.g., payment info additions across tests) showed no statistically significant differences, indicating changes were driven by random variance.

---

## 🔗 Interactive Dashboard
* 📊 **Tableau Dashboard:** https://public.tableau.com/app/profile/bartosz.cho.odzi.ski/viz/PortfolioProject2_17912004182610/Dashboard1?publish=yes

---

## 👤 Author
**Bartosz Chołodziński**
* 💼 LinkedIn: https://www.linkedin.com/in/bartosz-cholodzinski
* 📧 Email: bartosz.cholodzinski@gmail.com
