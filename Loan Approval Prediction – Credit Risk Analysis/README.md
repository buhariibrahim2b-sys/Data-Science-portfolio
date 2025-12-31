# Loan Approval Prediction – Credit Risk Analysis

## Project Overview
This project focuses on building a credit risk classification model to predict whether a loan application will be approved or rejected. Using historical customer financial and demographic data, the goal is to support data-driven lending decisions while balancing business growth and financial risk.

The project follows a complete end-to-end data science workflow, from data cleaning and exploratory analysis to model training, evaluation, and threshold tuning.

## Dataset
- Source: Kaggle – Analytics Vidhya: Loan Prediction Dataset
- Observations: 614
- Features: 14
- Target Variable: Loan_Status
   - Y = Loan Approved
   - N = Loan Rejected

The dataset contains applicant demographics, income information, loan characteristics, and credit history.

## Exploratory Data Analysis (EDA)

### Key steps performed:

- Examined loan approval vs rejection distribution

- Identified missing values across categorical and numerical features

- Analyzed the impact of Credit History, income, loan amount, and property area on approval rates

- Visualized distributions and relationships using histograms, boxplots, and count plots

## Key Insights:

- Applicants with a positive credit history are significantly more likely to be approved
- Income and loan amount distributions are skewed, requiring careful preprocessing
- The dataset shows realistic approval patterns typical of retail lending

## Data Cleaning & Preprocessing
### Missing Value Handling
- Categorical features: Imputed using the mode
- Numerical features: Imputed using the median to reduce the influence of outliers

## Feature Engineering

- Removed Loan_ID (identifier with no predictive value)

- Applied one-hot encoding to categorical variables

- Encoded target variable (Loan_Status) as binary (1 = Approved, 0 = Rejected)

- Standardized numerical features using StandardScaler

## Model Development
### Model Used

#### Logistic Regression

- Chosen for interpretability and suitability for binary classification in finance

- Commonly used in credit risk modeling

#### Train-Test Split

- 80% training, 20% testing

- Stratified split to preserve class distribution

## Model Evaluation
### Default Threshold (0.5)

- Accuracy: 0.86

- Recall (Approved loans): 0.99

- Precision (Approved loans): 0.84

This configuration prioritizes catching most eligible borrowers but allows more risky approvals.

## Threshold Tuning (0.7)

To reduce financial risk from false approvals, the decision threshold was increased to 0.7.
- Accuracy: 0.83

- Recall (Approved loans): 0.88

- Precision (Approved loans): 0.87

This trade-off improves loan quality at the cost of rejecting some eligible customers.

## ROC-AUC

- AUC Score: 0.85

This indicates strong ability to distinguish between approved and rejected loans and provides a more reliable evaluation metric than accuracy alone.

## Business Interpretation

- False Positives (approving risky loans) are more costly than false negatives

- Increasing the probability threshold helps reduce financial losses

- Threshold tuning enables alignment between the model and the organization’s risk appetite

## Key Takeaways

- Credit history is a dominant predictor in loan approval decisions

- Accuracy alone is insufficient for evaluating credit risk models

- Precision-recall trade-offs must be aligned with business objectives

- Logistic Regression provides both strong performance and interpretability

## Tools & Technologies

- Python

- Pandas, NumPy

- Matplotlib, Seaborn

- Scikit-learn

- Jupyter Notebook

## Future Improvements

- Experiment with alternative models (Random Forest, Gradient Boosting)

- Apply cross-validation for robustness

- Introduce cost-sensitive learning

- Test model generalization on unseen datasets
