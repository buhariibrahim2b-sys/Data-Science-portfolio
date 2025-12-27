# Customer Churn Analysis & Prediction
## Overview
Customer churn is a major challenge for subscription-based businesses. This project analyzes customer data to understand churn behavior and builds a predictive model to identify customers at risk of leaving. The objective is to support data-driven retention strategies and improve long-term customer value.

## Dataset
The project uses the Telco Customer Churn dataset sourced from Kaggle.
- Total records: 7,043
- Total features: 21
- Target variable: Churn (Yes / No)
The dataset includes customer demographics, account information, service usage, and billing details.

## Data Understanding & Preparation
The analysis began by exploring the dataset structure to understand feature types and data quality.

### Key actions:
- Checked the number of rows and columns
- Reviewed data types (numerical vs categorical)
- Verified missing values
- Generated summary statistics for numerical features

### Outcome:
- No missing values after preprocessing
- Dataset contained a mix of categorical and numerical variables
- Churn variable was imbalanced, with fewer churned customers

## Churn Rate Analysis
The churn rate was calculated to understand the severity of customer attrition.

### Outcome:
- Approximately 26.5% of customers churned
- About 73.5% of customers were retained

### Why this matters:
This confirmed that churn is a significant business issue and justified the need for predictive modeling.

## Exploratory Data Analysis (EDA)
EDA was conducted to identify patterns and relationships between customer features and churn.

### Key analyses included:
- Contract type vs churn
- Monthly charges vs churn
- Tenure vs churn
- Gender and demographic comparisons

### Key findings:
- Month-to-month contracts showed the highest churn
- Two-year contracts had the lowest churn
- Churned customers paid higher monthly charges on average
- Customers with longer tenure were less likely to churn

### Business insight:
Long-term contracts and customer loyalty reduce churn risk.

## Data Preprocessing
To prepare the data for modeling:

### Actions taken:
- Converted the target variable (Churn) into binary format
- Encoded categorical variables using one-hot encoding
- Scaled numerical features to ensure model stability

### Why this was done:
Logistic regression requires numerical, scaled input features for optimal performance.

## Model Building
A Logistic Regression model was trained to predict customer churn.

### Steps:
- Split data into training and testing sets
- Trained the model on the training data
- Evaluated performance on unseen test data

### Why Logistic Regression:
It is interpretable, efficient, and well-suited for binary classification problems like churn prediction.

## Model Evaluation

Model performance was evaluated using accuracy, precision, recall, and confusion matrix metrics.

### Initial outcome:
- High recall but moderate precision
- The model identified most churners but also flagged some non-churners

### Business implication:
The model was useful for identifying churn risk but could lead to unnecessary retention costs.

## Threshold Tuning

To balance business costs and model performance, the decision threshold was adjusted.

### What was done:
- Used predicted probabilities instead of default classification
- Increased the decision threshold to improve precision

### Outcome:
- Precision improved to 71%
- Recall decreased to 35%

### Business trade-off:
The tuned model reduced false positives but missed some churners, making it suitable when retention actions are costly.

## ROC Curve & AUC Analysis
Model discrimination ability was evaluated using ROC curve and AUC.

### Outcome:
- AUC score of 0.83
- Interpretation:

The model has strong ability to distinguish between churned and non-churned customers across different thresholds.

## Feature Impact Analysis
Model coefficients were analyzed to understand factors influencing churn.

### Features increasing churn risk:
- High total charges
- Short-term contracts

### Features reducing churn risk:
- Long customer tenure
- Two-year contracts

### Business insight:
Encouraging long-term contracts and rewarding loyal customers can reduce churn.

## Business Value
This project demonstrates how data science can support business decisions by:
- Identifying high-risk customers
- Optimizing retention strategies
- Balancing customer retention costs and churn prevention

## Tools & Technologies
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Jupyter Notebook

## Future Improvements
- Apply tree-based models (Random Forest, XGBoost)
- Address class imbalance using resampling techniques
- Incorporate cost-sensitive evaluation
- Deploy as a business dashboard

## Author
** Ibrahim Buhari **
Aspiring Data Scientist
