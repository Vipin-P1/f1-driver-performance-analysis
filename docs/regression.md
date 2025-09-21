## Regression

Regression analysis was used to examine relationships between Formula One performance variables, with the aim of predicting race outcomes and identifying the strongest influencing factors. Two approaches were applied:  
- **Linear regression**, run partly in Python ([notebook here](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/code/Linear%20Regression.ipynb)) and partly in SPSS, to model proportional, straightforward relationships.  
- **Non-linear regression**, performed in SPSS, to capture more complex patterns that reflect the unpredictable nature of racing.  

Together, these models highlight which features have the greatest predictive influence on lap performance and race outcomes.

---

### Correlation and Feature Selection

![Correlation Heatmap](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Correlation%20Heatmap%20-%20Avg%20Laptime%20Seconds.jpg)

Correlation analysis revealed that **FastestLapTimeSeconds** and **Qualifying1Seconds** had the strongest relationships with **AvgLapTimeSeconds**. Although some variables showed weaker correlations, all features were initially included in the regression model to ensure a comprehensive analysis.  

To refine the model, **backward elimination** was applied (SPSS), removing predictors with high p-values while monitoring overall performance metrics.

---

### Linear Regression Results

![Regression Tables](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Regression%20Tables.jpg)

The initial regression model (all features included) achieved an **R² value of 0.956**, indicating strong explanatory power. However, the **Durbin-Watson statistic of 0.288** suggested potential autocorrelation in the residuals, raising concerns about reliability.  

- Variables **Qualifying2Seconds** and **Qualifying3Seconds** had p-values > 0.05, suggesting limited impact.  
- Removing these predictors produced an **optimal regression model** with similar R² performance but reduced unnecessary complexity.  

**Regression Equation (Optimal Model):**

```text
AvgLapTimeSeconds = -2.61  
                  + 0.968 * FastestLapTimeSeconds  
                  + 0.014 * FastestLapSpeed  
                  + 0.064 * Qualifying1Seconds  
                  + 0.301 * AvgPitDuration  
                  - 0.201 * FastestPitstop


![Normal P-P Plot](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Normal%20P-P%20Plot%20Regression.jpg)

The **Normal Probability Plot** confirmed that residuals followed an approximately normal distribution, validating the model despite the autocorrelation concern.  

```

### Non-Linear Regression (SPSS)

![Non-Linear Regression Scores](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Non-Linear%20regression%20scores.jpg)

Non-linear regression (SPSS) was tested to capture quadratic and cubic relationships not addressed by the linear model. Key findings:  
- **Qualifying1Seconds** benefited most, with an **R² of 0.84** in cubic regression, highlighting a strong non-linear influence.  
- **Qualifying2Seconds** and **Qualifying3Seconds** improved moderately under non-linear models, suggesting effects missed by the linear approach.  
- Variables such as **FastestPitstop**, **AvgPitDuration**, and **FastestLapSpeed** showed weak predictive contributions across all models.  

![Curve Fit – Nonlinear Regression](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Curve%20Fit%20-%20Non-linear%20regression.jpg)

The curve fit for **Qualifying1Seconds** highlights its strong predictive power for lap time performance, reinforcing its role as a critical factor in race outcomes.

---

### Key Insights

- **FastestLapTimeSeconds** and **Qualifying1Seconds** are the strongest predictors of lap performance.  
- **Non-linear regression (SPSS)** revealed relationships missed by linear analysis, especially for qualifying variables.  
- **Pit stop variables**, while operationally important, showed limited statistical predictive power.  

Overall, regression analysis demonstrates that **qualifying performance** is a decisive factor in race outcomes, while pit stop efficiency plays a secondary role.
