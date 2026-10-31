# A/B Testing Case Study: White vs Black Website Background

An end-to-end A/B testing project that compares a white website background (control) with a black background (treatment) on user engagement and conversion.

**Tools:** Python, Pandas, SciPy, Statsmodels, Seaborn, Matplotlib

📄 **Full case study:** [[Case study document](https://github.com/merlin-data-analyst/AB-Testing-Case-Study/blob/main/about%20dataset.docx)]

---

## Business Question

Do users spend more time on a website with a white or a black background, and does either version have a higher conversion rate?

| Element | Definition |
|---|---|
| Group A (control) | White background |
| Group B (treatment) | Black background |
| Primary metric | Time spent per user |
| Secondary metric | Conversion rate (conversions ÷ users in group) |
| Significance level | α = 0.05 |

---

## Dataset

- **File:** `[ab_testing.csv](https://github.com/merlin-data-analyst/AB-Testing-Case-Study/blob/main/ab_testing_CSV.csv)`
- **Size:** 5,000 rows and 8 columns
- **Columns:** User ID, Group, Page Views, Time Spent, Conversion, Device, Location
- **Type:** Synthetic practice dataset representing an imaginary UK retail website

> The CSV has a Group column (A/B) but no Background column. The mapping A = White and B = Black comes from the project brief.

---

## Approach

1. **Define the question:** set the primary and secondary metrics before analysis.
2. **Inspect and clean:** checked shape, missing values, duplicates, data types and group labels.
3. **Map groups:** created a Background column (A = White, B = Black).
4. **Explore:** calculated group counts, means, medians and standard deviations.
5. **Test time spent:** used Welch's independent two-sample t-test, which does not assume equal variances.
6. **Test conversions:** used a two-proportion z-test.
7. **Visualise:** built a mean comparison chart and a boxplot.
8. **Recommend:** interpreted p-values, effect sizes, business relevance and limitations.

---

## Hypotheses

**Time spent:** H₀: mean time is equal for Black and White. H₁: mean time differs.

**Conversion:** H₀: conversion proportions are equal. H₁: conversion proportions differ.

---

## Key Results

| Metric | White (A) | Black (B) |
|---|---|---|
| Visitors | 2,519 | 2,481 |
| Conversions | 136 | 349 |
| **Conversion rate** | **5.40%** | **14.07%** |
| Absolute difference | Baseline | **+8.67 percentage points** |
| Relative lift | Baseline | **+160.55%** |
| Mean time spent | 241.73 | 243.30 |
| Median time spent | 241 | 244 |

| Test | Statistic | p-value | Result |
|---|---|---|---|
| Welch t-test (time spent) | t = 0.4695 | 0.6387 | **Not significant** |
| Two-proportion z-test (conversion) | z = 10.3545 | 3.99 × 10⁻²⁵ | **Significant** |

---

## Key Findings

- Black had a much higher observed conversion rate: **14.07% vs 5.40%**.
- The Black group converted **8.67 percentage points** higher, a relative lift of about **160.55%**.
- Average time spent barely differed (**243.30 vs 241.73**), and the difference was **not statistically significant** (p = 0.6387).
- A non-significant result does not prove the two backgrounds are equivalent. It means there is not enough evidence of a difference.

---

## Recommendation

Treat the black background as a **promising candidate for a controlled follow-up experiment, not an automatic permanent rollout.**

- Verify group assignment and data provenance.
- Run a real randomised experiment with users assigned randomly to each version.
- Define conversion as the primary outcome if it is the business goal.
- Keep content, layout, pricing, calls to action and traffic sources consistent.
- Check accessibility, readability, contrast and mobile rendering.
- Monitor guardrail metrics such as bounce rate, page load time, errors and customer satisfaction.
- Roll out gradually only if a real test reproduces the result.

---

## Limitations

- Synthetic data may not reflect real customer behaviour.
- The A = White, B = Black mapping is assumed from the project brief.
- Random assignment is not verified, so causal claims are not justified.
- Device and location differences were not segmented.
- Testing multiple outcomes can increase false-positive risk.
- Statistical significance is not the same as business value.
- No revenue column exists, so revenue impact cannot be calculated.

## Project Structure

```
├── ab_testing.csv
├── ab_test_analysis.py
├── average_time_comparison.png
├── time_spent_distribution.png
└── README.md
---

## Skills Demonstrated

A/B Testing | Hypothesis Testing | Welch's t-test | Two-Proportion Z-test | Conversion Rate Analysis | Data Cleaning | Descriptive Statistics | Data Visualisation | Statistical Interpretation | Business Recommendations

---

## Author

**Merlin Keerthana K A** | Aspiring Data Analyst

🔗 [LinkedIn](https://www.linkedin.com/in/merlin-keerthana)
📧 merlink470@gmail.com
🐙 [GitHub](https://github.com/merlin-data-analyst)
