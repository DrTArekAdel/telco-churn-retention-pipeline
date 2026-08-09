# Telco Customer Churn Analysis

Exploratory data analysis and churn-driver identification on IBM's public Telco Customer Churn dataset (7,043 customers, 21 features), using Python and pandas.

## Objective
Identify which customer, service, and billing attributes are most associated with churn, and translate the findings into concrete retention actions.

## Tech Stack
Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

## Approach
1. **Data cleaning** — coerced `TotalCharges` to numeric, identified and handled 11 missing values (all customers with 0-month tenure), checked for duplicates and inconsistent categorical labels.
2. **Exploratory analysis** — examined churn rate by contract type, payment method, internet service type, tenure, and monthly charges.
3. **Segmentation** — grouped customers by pricing tier and service type to isolate where churn concentrates.

## Key Findings
- Churn is concentrated among **month-to-month contracts**; 1- and 2-year contracts show substantially lower attrition.
- Customers paying by **electronic check** churn at a notably higher rate than those on automatic payment methods.
- Churn rises for customers in the **$70–$110 monthly charge range**.
- **Fiber optic** internet subscribers make up a disproportionate share of churned customers relative to their share of the customer base — worth investigating as a service-quality issue rather than assuming it's price-driven.
- New customers (tenure = 0) had missing `TotalCharges` by definition; these were corrected rather than dropped, to avoid biasing the sample toward existing customers.

## Business Recommendations
- Prioritize retention outreach for month-to-month customers, particularly in their first 12 months.
- Investigate service quality specifically for fiber optic customers before assuming price is the primary churn driver.
- Incentivize migration from electronic check to autopay (e.g., a one-time bill credit).

## Limitations
This is a single cross-sectional snapshot with no time-series or causal data — the findings describe *association*, not proven causation, and would need a controlled test (e.g., an A/B retention offer) to validate before rollout.

## Files
- `IBM Final.ipynb` — full analysis notebook
- `WA_Fn-UseC_-Telco-Customer-Churn.csv` — source data (https://www.kaggle.com/datasets/palashfendarkar/wa-fnusec-telcocustomerchurn/data)

## How to Run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook "IBM Final.ipynb"
```
