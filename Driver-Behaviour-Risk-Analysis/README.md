# Driver Behaviour Risk Analysis (Telematics-Style Project)
## Project Overview

This project applies data science techniques to sensor based driver behaviour data, similar to telematics systems used in motor insurance. The goal is to identify risky driving patterns and demonstrate how insurers can leverage behavioural data to improve pricing, underwriting, and risk management decisions.

## Business Objective

To analyze driving behaviour using motion sensor data and build a predictive model that classifies drivers as risky or safe, supporting:

- Fairer insurance pricing
- Improved underwriting decisions
- Reduced accident and claim risk

## Dataset Description
The dataset contains smartphone sensor readings collected during driving session:

- Accelerometer (X, Y, Z): measures linear acceleration (e.g., braking, acceleration)
- Gyroscope (X, Y, Z): measures rotational movement (e.g., turning, stability)

These sensors closely resemble inputs used in real-world telematics and usage-based insurance products.

##  Data Preparation & Feature Engineering
Raw, high-frequency sensor readings were transformed into interpretable driver-level features:

- Acceleration magnitude
- Rotation magnitude
- Summary statistics (mean, standard deviation, maximum values)

This feature engineering approach mirrors how insurers aggregate raw telematics signals into behavioural risk indicators.

## Modelling Approach

- Model: Logistic Regression (chosen for interpretability)
- Preprocessing: Feature scaling using StandardScaler
- Evaluation metrics: Accuracy, Precision, Recall
- Focus: Balanced detection of risky drivers while limiting false positives

To enable modelling, a synthetic driver population was generated based on observed sensor statistics.

## Model Performance

### The final model achieved:
- Accuracy: 75%
- Precision: 77%
- Recall: 74%

These results indicate a balanced ability to identify risky drivers while maintaining reasonable precision, which is important in insurance pricing contexts.

## Key Risk Drivers

Feature interpretation revealed that the strongest indicators of risky driving were:
- Sharp turning behaviour (gyro_max)
- Harsh acceleration or braking events (acc_max)
- High variability in acceleration (acc_std)

Conversely, predictable and stable turning behaviour (gyro_std) was associated with lower risk.

## Business Insights

- Aggressive manoeuvres such as sharp turns and harsh braking are strong predictors of driving risk.
- Behavioural data provides actionable insights that can support pricing differentiation and underwriting decisions.
- Interpretable models allow insurers to clearly explain why certain drivers are classified as higher risk.

## Limitations & Notes

- The project focuses on behavioural patterns rather than precise location or speed data.
- Synthetic samples were generated to demonstrate modelling techniques; results are illustrative and intended for learning and portfolio purposes.

## Tools & Technologies
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook

## Career Relevance

### This project demonstrates:

- Practical application of data science to insurance style problems
- Feature engineering from real sensor data
- Interpretable machine learning for risk analysis
- Clear communication of technical results to business stakeholders
