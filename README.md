# UAE Used Car Depreciation & Acquisition Pricing

## Business Problem
Does a car's age and mileage alone explain its resale price — or do the economic 
conditions it was built into (inflation, oil prices, regional conflict) matter 
just as much? And does the pace of depreciation actually differ across distinct 
economic eras?

## Dataset
2,000 used car listings scraped from YallaMotor (UAE) in mid-2026, joined with 
macroeconomic indicators (inflation, oil price, conflict index) by production 
year, spanning 16 unique production years across four analytical eras: 
Pre-COVID, COVID, Semiconductor Shortage, and Conflict-Driven.

## Notebook
`1_EDA_Car_Age.ipynb` — Data cleaning, VIF diagnostics for multicollinearity
`2_Models_Car_Age.ipynb` —  three OLS regression models (baseline, macroeconomic-interaction, era-stratified).

## Methodology
1. Tested raw macroeconomic variables for multicollinearity with vehicle age 
   (VIF as high as 209.9); resolved by routing macro influence through 
   age-interaction terms rather than standalone predictors
2. **Model A** — baseline hedonic regression (age, mileage, categorical controls)
3. **Model B** — adds three macroeconomic interaction terms to test moderation effects
4. **Model C** — stratifies the dataset into four economic eras to test whether 
   depreciation rates differ significantly between them

## Key Findings
- Model A explained 44.8% of price variance (Adj. R² = 0.438); age (−2.8%/yr) 
  and mileage (−4.8%/10,000 km) were both significant depreciation drivers
- Model B's macroeconomic interactions were jointly significant (F = 4.00, p = 0.008)
- Model C found depreciation was steep pre-Covid (−8.1%/yr) and steeper still 
  during Covid (−18.3%/yr) — but undetectable during the semiconductor-shortage 
  and conflict-driven periods, a range-restriction limitation from limited price 
  variation in still-young vehicle cohorts, not evidence depreciation stopped

## Tools
Python (pandas, statsmodels), Google Colab

## How to Run
Open the notebook in Google Colab or Jupyter. Requires: pandas, statsmodels, 
numpy, matplotlib/seaborn.

## Full Case Study
[Read the full write-up on my portfolio →](your-framer-link.com/projects/uae-car-pricing)
