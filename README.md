# Customer Churn Prediction using Machine Learning

## Project Overview

This project aims to predict customer churn for a telecommunications company using supervised machine learning models.

Customer churn refers to the situation where a customer stops using a company's services. Predicting churn can help companies identify at-risk customers and design retention strategies.

## Objective

The main objective of this project is to build and evaluate machine learning models capable of predicting whether a customer is likely to churn based on demographic, account, service, and billing information.

## Dataset

The project uses the Telco Customer Churn dataset.

Each row represents a customer, and each column contains information about the customer.

The dataset includes:

- demographic information;
- services subscribed by each customer;
- account information;
- billing information;
- churn status.

The target variable is `Churn`, which indicates whether the customer left the company or not.

## Methodology

The project follows a complete machine learning workflow:

1. Data loading and understanding.
2. Data cleaning.
3. Exploratory Data Analysis.
4. Feature preprocessing.
5. Train-test split.
6. Model training.
7. Model evaluation.
8. Feature importance analysis.
9. Business interpretation of the results.

## Data Cleaning

The following cleaning steps were performed:

- `TotalCharges` was converted from object type to numeric type;
- missing values created after conversion were removed;
- the target variable `Churn` was encoded as:
  - `0` = No Churn;
  - `1` = Churn;
- the variable `customerID` was removed because it is only an identifier.

## Exploratory Data Analysis

The exploratory analysis showed several important patterns:

- customers with month-to-month contracts have the highest churn rate;
- customers with lower tenure are more likely to churn;
- customers with higher monthly charges tend to have higher churn risk;
- customers using fiber optic internet service have a higher churn rate;
- customers paying by electronic check show the highest churn rate among payment methods.

## Models Used

Three classification models were trained and compared:

- Logistic Regression;
- Random Forest;
- Gradient Boosting.

## Evaluation Metrics

The models were evaluated using:

- Accuracy;
- Precision;
- Recall;
- F1-score;
- ROC-AUC.

## Model Results

The Gradient Boosting model achieved the best overall performance based on ROC-AUC.

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Gradient Boosting | 0.796 | 0.641 | 0.529 | 0.580 | 0.839 |
| Logistic Regression | 0.726 | 0.490 | 0.797 | 0.607 | 0.835 |
| Random Forest | 0.784 | 0.622 | 0.476 | 0.539 | 0.812 |

## Best Model

The best model selected based on ROC-AUC is:

**Gradient Boosting**

The model achieved a ROC-AUC score of approximately **0.84**, which indicates a good ability to distinguish between churn and non-churn customers.

## Feature Importance

The feature importance analysis showed that the most important variables for predicting churn are:

- `Contract`;
- `tenure`;
- `InternetService`;
- `MonthlyCharges`;
- `TotalCharges`;
- `OnlineSecurity`;
- `TechSupport`;
- `PaymentMethod`.

These results are consistent with the exploratory analysis and provide useful business insights.

## Key Business Insights

The analysis suggests that the customers most at risk of churn are generally those who:

- have month-to-month contracts;
- have low tenure;
- pay higher monthly charges;
- use fiber optic internet service;
- pay by electronic check;
- do not have some support or security services.

These insights can help a company design targeted customer retention strategies.

## Project Structure

```text
customer-churn-prediction/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── figures/
│   ├── churn_distribution.png
│   ├── churn_by_contract.png
│   ├── tenure_by_churn.png
│   ├── monthly_charges_by_churn.png
│   ├── churn_by_internet_service.png
│   ├── churn_by_payment_method.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── feature_importance.png
│
├── notebook/
│   └── churn_analysis.ipynb
│
├── model_results.csv
├── README.md
└── requirements.txt
```