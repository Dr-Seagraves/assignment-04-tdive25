# Assignment 04 Interpretation Memo

**Student Name:** Trenton Diveley
**Date:** 2/13/26
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors:

| Model | Y Variable | X Variable | Interpretation Focus |
|-------|------------|------------|----------------------|
| 1 | ret (annual) | div12m_me | Dividend yield |
| 2 | ret (annual) | prime_rate | Interest rate sensitivity |
| 3 | ret (annual) | ffo_at_reit | FFO to assets (fundamental performance) |

For each model, summarize the key results in the sections below.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): [0.1082] (SE: [0.006], p-value: [0.000])
- Slope (β₁): [-0.0687] (SE: [0.032], p-value: [0.035])
- R²: [0.002] | N: [2527]

**Model 2: ret ~ prime_rate**
- Intercept (β₀): [0.1998] (SE: [0.016], p-value: [0.000])
- Slope (β₁): [-0.0194] (SE: [0.003], p-value: [0.000])
- R²: [0.016] | N: [2527]

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): [0.0973] (SE: [0.009], p-value: [0.000])
- Slope (β₁): [0.5770] (SE: [0.567], p-value: [0.309])
- R²: [0.000] | N: [2518]

*Note: Model 3 may have fewer observations if ffo_at_reit has missing values; statsmodels drops those rows.*

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- A 1 percentage point increase in dividend yield (12-month dividends / market equity) is associated with a [-0.0687] change in annual return.
- Your interpretation: It is associated with just slightly lower returns since higher dividend yield investments tend to cut dividends, leading to less return.

**Prime Loan Rate (prime_rate):**
- A 1 percentage point increase in the year-end prime rate is associated with a [-0.0194] change in annual return.
- Your interpretation: Yes, REIT returns are sensitive to interest rates in a negative way as higher interest rates can lead to more cash outflow, leading to an investment yielding less overall annual returns as some of that return is mitigated by interest rates.


**FFO to Assets (ffo_at_reit):**
- A 1 unit increase in FFO/Assets (fundamental performance) is associated with a [0.5770] change in annual return.
- Your interpretation: Yes, a higher performance leads to a positive increase in return. Higher performance investments will typically yield a higher return and this is proven significantly here as the slop of 0.5770 is the largest of our 3 regressions. However, that is not necessarily always the case, and will be discussed later with variable significance.
---

## 4. Statistical Significance

For each slope, at the 5% significance level:
- **div12m_me:** It is significant since the p value of 0.035 is less than 0.05. This shows that dividend yield does indeed have an effect on annual return.
- **prime_rate:** It is significant since the p value is 0.000 which is well below our significance level of 0.05. This shows that annual return has a very strong correlation with interest rate.
- **ffo_at_reit:** Not significant as the p value of 0.309 is larger than 0.05. This shows that high performance doesn't have a strong correlation with annual return with this data presented.

**Which predictor has the strongest statistical evidence of a relationship with annual returns?** Prime Loan Rate as the p value was 0.000 showing that it has the strongest correlation between the 3 comparisons.

---

## 5. Model Fit (R-squared)

Compare R² across the three models:
- Your interpretation: The prime loan rate R^2 has an R^2 of 0.016 meaning that 1.6% of the variation is explained. While that doesn't seem like much, it is more compared the the 0.002 and 0.000 that the other 2 models produced. Overall, low R^2 across the board, showing that while these 3 factors should be considered for REIT returns, there are many other factors that come into play that would need compared as well to get a full understanding of how the returns fluctuate. 
---

## 6. Omitted Variables

By using only one predictor at a time, we might be omitting:
- [Variable 1]: Dividend yield matters since higher amounts of dividends distributed by a company can also lead to more dividends cut, showing risk.
- [Variable 2]: Prime Loan Rate matters as higher interest rates can lead to less overall gain on investments.
- [Variable 3]: Higher performance of a company can typically lead to better investment returns.

**Potential bias:** If omitted variables are correlated with both the X variable and ret, our slope estimates may be biased. 

---

## 7. Summary and Next Steps

**Key Takeaway:**
The predictors with the strongest correlation are the dividend yield and the interest rate. This on the surface makes sense as these are 2 factors companies look at when making investments. However, our R^2 values show that we'd need more information or predictors to make a solid prediction about the returns as a whole. 

**What we would do next:**
- Extend to multiple regression (include two or more predictors)
- Test for heteroskedasticity and other OLS assumption violations
- Examine whether relationships vary by time period or REIT sector

---

## Reproducibility Checklist
- [Y] Script runs end-to-end without errors
- [Y] Regression output saved to `Results/regression_div12m_me.txt`, `regression_prime_rate.txt`, `regression_ffo_at_reit.txt`
- [Y] Scatter plots saved to `Results/scatter_div12m_me.png`, `scatter_prime_rate.png`, `scatter_ffo_at_reit.png`
- [Y] Report accurately reflects regression results
- [Y] All interpretations are in economic units (not just statistical jargon)
