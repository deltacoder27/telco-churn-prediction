# Telco Customer Churn Prediction

## Overview

This project builds a logistic regression model to predict customer churn for a telecommunications company. The goal is to identify at-risk customers and provide actionable recommendations to reduce churn.

## Dataset

- **Source:** IBM Telco Customer Churn Dataset (Kaggle)
- **Records:** 7,032 customers
- **Features:** 20 customer characteristics (demographics, services, billing)
- **Target:** Churn (Yes/No)

## Project Structure

- **data/** - All datasets
  - raw/ - Original Kaggle dataset
  - processed/ - Cleaned and encoded data
- **notebooks/** - Jupyter notebooks (in order)
  - 01_exploration_and_cleaning.ipynb
  - 02_eda_and_feature_engineering.ipynb
  - 03_modeling_and_recommendations.ipynb
- **README.md** - This file

## Methodology

### Week 1: Data Cleaning
- Handled missing values in TotalCharges column
- Removed new customers (tenure=0) with incomplete churn history
- Converted data types and validated data quality

### Week 2: Exploratory Data Analysis & Feature Engineering
- Analyzed churn rates by categorical features (contract type, internet service, security)
- Compared metrics between churners and non-churners
- Encoded categorical variables using label encoding and one-hot encoding

### Week 3: Logistic Regression Modeling
- Built logistic regression model with standardized features
- Optimized decision threshold (0.3) to maximize recall
- Identified top features driving churn prediction

## Key Findings

**Features Preventing Churn:**
1. Tenure (longest tenure = lowest churn)
2. Two-year contracts
3. Online security services

**Features Driving Churn:**
1. Month-to-month contracts (42.7% churn rate)
2. Fiber optic internet service (41.9% churn rate)
3. Streaming services

## Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 75.41% |
| Precision | 52.57% |
| Recall | 76.47% |
| F1-Score | 62.31% |

The model prioritizes **recall** to catch 76% of actual churners, I focused on catching as many churners as possible, even though it means spending retention budget on some people who wouldn't have left anyway. But missing someone who actually leaves is worse than wasting budget on a false alarm.

## Business Recommendations

1. **Promote longer contracts with bundled online security** — Offer discounts on 2-year contracts bundled with online security, especially targeting new customers with high monthly charges.

2. **Investigate fiber optic service quality** — Launch customer surveys and competitive benchmarking to understand why fiber optic customers churn at higher rates.

## How to Use

1. Clone this repository
2. Review the notebooks in order (01, 02, 03)
3. Explore the data in `data/processed/`
4. Adapt the model for your own churn prediction use case

## Technologies

- Python 3.8+
- pandas, numpy (data manipulation)
- scikit-learn (machine learning)
- matplotlib, seaborn (visualization)

## Author

Arkya Ghosh

## License

MIT License - feel free to use this project for learning purposes.
