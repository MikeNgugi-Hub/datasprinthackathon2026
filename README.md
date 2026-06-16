# DataSprint 2026 — Kenya FinAccess Financial Inclusion Challenge
**Strathmore Data Community × iLab Africa**

## Team Name
Tres Amigos

## Team Members
- Emmanuel Kiptoo
- Mutua Ian Mwenda
- Michael Ng'ang'a Ngugi

## Problem Statement
Using data from 20,871 Kenyan adults surveyed in 2024, we built a machine learning model to predict whether a person's financial situation Improved, Stayed the Same, or Worsened compared to the previous year.
We also identified the key factors driving financial outcomes in Kenya.

## Dataset
2024 FinAccess Household Survey published by the Central Bank of Kenya, KNBS, and FSD Kenya. The curated dataset contains 20,871 rows and 28 columns covering demographics, livelihood, mobile access, financial behaviour, and financial health indicators.

## Tools and Libraries Used
- Python 3.12
- pandas, numpy for data manipulation
- matplotlib, seaborn for visualisation
- scikit-learn for Decision Tree, Logistic Regression, and Random Forest models
- XGBoost for gradient boosting
- imbalanced-learn for SMOTETomek class balancing
- Kaggle Notebooks as the development environment

## Methodology

### 1. Data Cleaning
- Filled 5,734 missing values in barriers_bank with No barrier
- Cleaned education_level values by removing quote marks and extra spaces
- Grouped unknown marital status values
- Created log income column to handle skewed income distribution

### 2. Feature Engineering
Created 9 new features:
- financial_resilience_score: composite score of 5 financial safety signals
- vulnerability_index: combination of shock, debt, food insecurity signals
- high_risk: flag for triple risk combination
- savings_any, loan_any, debt_burden
- income_band, mobile_fully_included, inclusion_score

### 3. Class Imbalance Handling
Applied SMOTETomek to balance the training set from 52/27/21 split
to equal representation of all three classes.

### 4. Models Trained
1. Decision Tree with class_weight balanced
2. Logistic Regression with class_weight balanced
3. Random Forest with 300 trees and class_weight balanced
4. XGBoost with 500 trees
5. Ensemble Voting Model combining Random Forest and XGBoost

### 5. Evaluation
Primary metric: Weighted F1 Score
Train/test split: 80% training, 20% testing with stratification

## Key Findings
1. Food insecurity is the single strongest predictor of financial deterioration
2. People who experienced a financial shock were significantly more likely to report Worsened finances
3. The Improved group had a median income 73% higher than the Worsened group
4. Rural respondents had higher Worsened rates than urban respondents
5. Composite risk features outperformed individual variables in predictive power

## Model Performance
Best model: Ensemble (Random Forest + XGBoost)
Weighted F1 Score: 0.5305

## Recommendations
1. Food and basic security should be prioritised before financial products
2. Low-barrier emergency savings accounts for rural and low-income households
3. Expand index insurance and social safety nets in shock-prone counties
4. Reduce mobile money barriers in rural areas
5. Invest in financial literacy programmes for low-income communities

## Repository Structure
- notebook: Jupyter notebook with full pipeline
- visualisations: All 11 charts as PNG files
- presentation: 7-slide PowerPoint presentation
