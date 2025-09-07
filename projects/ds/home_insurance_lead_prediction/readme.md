# Home Insurance Lead Prediction Model

## Overview
This project focuses on building a **Lead Prediction Model** for home insurance.  
Insurance agents often receive a large number of leads (quotes), but only a fraction convert into active policies.  
The goal is to help agents **prioritize leads** by assigning a **Lead Conversion Score**, enabling them to focus on the most promising opportunities.

## Business Problem
- Agents receive thousands of home insurance quotes.
- Only a subset of these quotes eventually convert into policies.
- Manual prioritization is inefficient and may lead to missed opportunities.
- A data-driven scoring model can improve efficiency and increase conversion rates.

## Data
The dataset includes historical home insurance leads, enriched with policyholder and property characteristics.  
Sample features include:
- **House Age**: Age of the property in years.  
- **House Value**: Estimated market value of the home.  
- **Insured Occupation**: Occupation category of the primary insured.  
- **Annual Income**: Household income of the insured.  
- **Prior Claims**: Number of claims filed in the past.  
- **Credit Score**: Creditworthiness of the insured.  
- **Conversion** *(Target)*: Binary indicator (1 = converted to policy, 0 = not converted).

## Methodology
1. **Data Preparation**  
   - Clean missing values and handle categorical variables.  
   - Standardize and scale continuous features.  
   - Train-test split to evaluate performance.

2. **Exploratory Data Analysis (EDA)**  
   - Distribution analysis of home values, incomes, and credit scores.  
   - Conversion rate by occupation, income level, and claims history.  

3. **Modeling**  
   - Baseline: Logistic Regression.  
   - Tree-based: Random Forest, Gradient Boosting (XGBoost/LightGBM).  
   - Performance metrics: **AUC-ROC, Precision-Recall, Accuracy, F1**.  

4. **Lead Conversion Score**  
   - Each lead is assigned a probability score between 0 and 1.  
   - Higher scores indicate higher likelihood of conversion.  
   - Agents can sort and prioritize leads accordingly.

## Results
- Gradient Boosting achieved the best predictive performance (AUC ~0.82 on test set).  
- Agents can now focus on the **top 20% of leads**, expected to yield **60% of actual conversions**.  

## Tools & Technologies
- **Python, Jupyter Notebook**  
- **Pandas, NumPy, Scikit-Learn, XGBoost**  
- **Matplotlib, Seaborn** for visualization  

## Portfolio Value
This project demonstrates the ability to:  
- Translate a **business need into a data science solution**.  
- Handle structured insurance data.  
- Apply **predictive modeling** for real-world impact.  
- Deliver an interpretable solution for business stakeholders.
