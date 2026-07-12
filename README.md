# Marketing Mix Modelling & Causal Inference
**R | fixest | ggplot2 | IV Regression | 2SLS | A/B Testing | RDD**

Econometric analysis of price elasticity and marketing effectiveness 
for a retail TV dataset, applying OLS regression, instrumental variable 
(2SLS) correction for endogeneity, experimental A/B/N test design, 
and Regression Discontinuity Design for causal inference.


## Overview

This project applies modern econometric and causal inference methods 
to a retail pricing dataset of 2,080 TV product-week observations 
across four major brands. Starting from descriptive analytics and 
OLS regression, the analysis identifies and corrects for endogeneity 
in price using a cost shifter instrument, then designs an A/B/N 
experiment and proposes a natural experiment (RDD) to answer causal 
questions about ratings and sales.


## Key Skills Demonstrated

- **Descriptive analytics** — brand-level dollar sales ranking, 
  scatter plot visualisation, correlation analysis using ggplot2
- **OLS regression** — marketing mix model with price and marketing 
  spend as predictors, coefficient interpretation
- **Endogeneity diagnosis** — identifying omitted variable bias, 
  reverse causality, and measurement error in price
- **Instrumental variable regression (2SLS)** — first-stage and 
  second-stage regression using cost_shifter, comparing OLS vs IV 
  estimates to demonstrate endogeneity correction
- **Statistical judgment** — interpreting when a positive OLS 
  coefficient is biased, and what the IV estimate reveals causally
- **A/B/N test design** — randomisation unit selection, 10/10/80 
  treatment/control split, power analysis using pwr package, 
  covariate balance checks
- **Regression Discontinuity Design** — natural experiment proposal 
  for estimating causal effect of Amazon star ratings on sales


## Methods & Tools

| Task | Package / Method |
|---|---|
| Data wrangling | dplyr, tidyverse |
| OLS & IV regression | fixest::feols() |
| Regression output | modelsummary |
| Visualisation | ggplot2, geom_point() |
| Power analysis | pwr::pwr.t.test() |
| Fixed effects | brand, technology, resolution, HDR |


## Results Summary

| Model | Price Coefficient | Interpretation |
|---|---|---|
| OLS (Equation 1) | +0.618*** | Biased — endogeneity |
| OLS with fixed effects | +0.672*** | Still biased |
| 2SLS IV (cost_shifter) | -0.734*** | Causal estimate |

The OLS estimate is upward biased due to omitted variable bias 
(premium product quality correlated with both price and sales). The 
IV estimate corrects this, revealing a true negative causal effect 
of price on sales — consistent with standard demand theory.

## Key Finding

OLS regression produced a counterintuitive positive price-sales 
relationship (+0.618) driven by endogeneity. Introducing a cost 
shifter instrument via 2SLS corrected this bias, revealing the true 
causal effect of -0.734 — confirming that higher prices reduce 
demand when product quality confounders are properly controlled for.


## Academic Context

Completed as part of MSIN0094 — Marketing Analytics, MSc Business 
Analytics, UCL School of Management, 2024/25.
