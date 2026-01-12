Project Overview
Financial fraud costs institutions over $30B annually. Traditional rule-based detection methods often fail to catch evolving fraud schemes and generate a high number of false positives.
This project builds a machine learning-based fraud detection system using real transaction data to detect anomalies and classify fraudulent activity with high accuracy.

Objectives
Detect fraudulent bank transactions using ML
Identify patterns and key risk indicators behind fraud
Improve detection accuracy while reducing false alarms
Build a scalable framework for real-world deployment
Dataset Overview
Property	Details
Source	Kaggle – Bank Transaction Dataset
Rows	2,512 transactions
Features	Amount, Transaction Type, Timestamp, Account Balance, Device ID, IP, Browser
Data Quality	✅ No missing or duplicate values
Data Preprocessing & Feature Engineering
Created new features:
✅ TransactionHour, DayOfWeek, Weekend vs Weekday
✅ Amount-to-Balance Ratio, TimeSinceLastTransaction
✅ Deviation from user’s historical transaction behavior
Categorical encoding & irrelevant ID removal
Final dataset: 32 features
Exploratory Data Analysis
✔ Fraud transactions often show high value with low account balance
✔ Younger users → frequent smaller transactions
✔ Most fraud occurs between 10AM–4PM on weekdays & month-end
✔ Credit transfer & debit card transactions are most common

Machine Learning Workflow
Anomaly Detection – Isolation Forest**
Contamination rate: 5%
Identified 126 suspicious transactions
Fraud Classification – Random Forest**
Metric	Score
Accuracy	97%
Precision (Fraud)	0.81
Recall (Fraud)	0.52
F1 Score	0.63
Hyperparameter Tuning**
GridSearchCV + 5-fold CV
Best Params: n_estimators=200, max_depth=10, max_features='sqrt'
Key Fraud Indicators
Indicator	Description
High transaction amount vs low balance	Strongest predictor of fraud
Rapid multiple transactions	Short time intervals between transactions
Multi-location logins	Suspicious geographic activity
Failed login attempts	Correlates strongly with fraud cases
Recommendations
Area	Recommendation
Detection	Use hybrid approach: Isolation Forest + Random Forest
Deployment	Build real-time alert pipeline via APIs
Optimization	Automate retraining with new fraud data
Monitoring	Create investigation dashboards for fraud analysts
