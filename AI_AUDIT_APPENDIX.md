# AI Audit Appendix (Assignment 04)

## Tool(s) Used
- GitHub AI Agent

## Task(s) Where AI Was Used
- To help code the regression script.

## Prompt(s)
- Help me code all sections labeled TODO in assignment04_regression.py. For Context, this code will be used to estimate 3 linear regressions, save them, and then create a scatter plot.

## Output Summary
- I'll start by reading the assignment04_regression.py file to see all the TODO sections. 

Read [](file:///workspaces/assignment-04-tdive25/assignment04_regression.py)

Now I'll implement all the TODO sections. Let me identify and code them: 

Replacing 60 lines with 112 lines in [](file:///workspaces/assignment-04-tdive25/assignment04_regression.py)


```

```
Perfect! Now let me verify the implementation works by running the script: 

Ran terminal command:  cd /workspaces/assignment-04-tdive25 && python assignment04_regression.py

Excellent! All TODOs have been successfully implemented and the script ran perfectly! Here's what was completed:

## ✅ Implemented Sections:

1. **`estimate_regression()`** - Fits OLS regression using `statsmodels.formula.api.ols()` and returns the fitted model

2. **`save_regression_summary()`** - Saves the regression summary statistics to text files in the Results directory

3. **`plot_scatter_with_regression()`** - Creates professional scatter plots with:
   - Data points with transparency (alpha=0.5)
   - Fitted regression line overlaid in red
   - Axis limits zoomed to 2nd-98th percentiles for better visualization
   - Title with R² value displayed
   - Saved at 300 DPI for high quality

4. **`print_key_results()`** - Displays comprehensive regression results including:
   - Coefficients (intercept & slope) with standard errors
   - T-statistics and p-values
   - R² and Adjusted R²
   - Sample size (N)
   - Interpretation of whether the slope is significant at the 5% level

## 📊 Results Summary:

The script estimated three regressions and saved:
- **regression_div12m_me.txt** - Dividend yield regression (negative, significant)
- **regression_prime_rate.txt** - Prime rate regression (negative, highly significant)  
- **regression_ffo_at_reit.txt** - FFO/Assets regression (positive, not significant)
- Plus corresponding scatter plots with fitted lines

All outputs are saved in the Results directory and ready for your interpretation memo!

Made changes.

## Verification & Modifications (Disclose • Verify • Critique)
- **Verify:** Ran the script and results came out as expected!
- **Critique:** Not Much!
- **Modify:** None.

## If No AI Tools Used
Write: "No AI tools were used for this assignment."
