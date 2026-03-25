# Telecom Customer Retention & Churn Analysis

## Overview

This project analyzes customer churn in a telecommunications company using subscription patterns, usage behavior, and payment information. The goal is to identify at-risk customers and provide actionable strategies to improve retention and maximize revenue.

Reducing churn is critical for subscription-based companies, as it directly affects customer lifetime value (CLV) and profitability. This analysis combines exploratory data insights with predictive modeling to deliver business-ready recommendations.

---

## Dataset Summary

The dataset contains 7,043 customer records with 21 features. The `Churn` column indicates whether a customer has left the company. Key attributes include demographics, subscription types, contract details, and payment methods.

**Key Observations:**  
- Around 26% of customers have churned.  
- Features such as `Contract`, `PaymentMethod`, and `MonthlyCharges` are strongly linked to churn.  
- Missing values exist mainly in `TotalCharges` and were handled during preprocessing.  

---

## Data Preparation

Data cleaning and preprocessing included:  
1. Filling missing `TotalCharges` with median values.  
2. Converting categorical features into numeric values using label encoding or one-hot encoding.  
3. Correcting data types and removing duplicate records.  
4. Creating additional features to improve model performance (see Feature Engineering).

---

## Feature Engineering

New features were added to better understand customer behavior:  
- **MonthlyAverageCharge:** TotalCharges divided by tenure to measure spending.  
- **HighValueCustomer:** Indicator for customers paying above the average.  
- **TotalSubscribedServices:** Number of services each customer subscribes to.  
- **TenureSegment:** Groups customers into short-term, mid-term, and long-term categories.  
- **CustomerCluster:** KMeans clustering for segmenting similar customer types.

These features improve prediction accuracy and provide actionable insights for retention.

---

## Exploratory Analysis

EDA revealed important patterns:  
- **Contract Type:** Month-to-month customers show the highest churn; long-term contracts are more loyal.  
- **Payment Method:** Customers using electronic checks have higher churn compared to auto-pay users.  
- **Tenure:** Customers with less than 12 months tenure are more likely to churn.  
- **Monthly Charges:** Higher bills correlate with higher churn, particularly for month-to-month customers.  
- **Service Engagement:** Customers with multiple subscriptions are less likely to churn.

Charts and heatmaps were used to visualize trends and relationships.

---

## Predictive Modeling

**XGBoost** was used for churn prediction due to its performance and ability to handle imbalanced data. Steps included:  
1. Splitting data into training (80%) and testing (20%) sets.  
2. Oversampling minority class using ADASYN.  
3. Hyperparameter tuning with GridSearchCV.  
4. Model evaluation using ROC-AUC, precision, recall, and F1-score.

**Performance Metrics:**  
- Accuracy: 85%  
- ROC-AUC: 0.88  
- Precision (churn class): 0.79  
- Recall (churn class): 0.74  

Top predictors: **Contract type**, **Tenure**, **MonthlyCharges**, **PaymentMethod**.

---

## Business Insights

1. **High-Risk Segment:** Month-to-month, short-tenure, high-billing customers are most likely to churn.  
2. **Retention Strategies:** Encourage auto-pay, offer long-term contract discounts, and bundle services.  
3. **Engaged Customers:** Multi-service users have higher retention and are ideal candidates for upselling.  
4. **Payment Behavior:** Electronic check users may require reminders or alternative billing options.

---

## Recommendations

- Targeted campaigns for at-risk customers.  
- Encourage contract upgrades to 12- or 24-month plans.  
- Personalized offers for high-value customers.  
- Promote multi-service subscriptions to increase engagement.  
- Integrate churn scoring into CRM systems for proactive interventions.

---

## Deployment & Visualization

- Build dashboards to monitor churn trends and segment risk.  
- Automate updates from billing systems for real-time predictions.  
- Integrate predictive insights into CRM to trigger retention campaigns.

---

## Tools & Technologies

- Python: pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost, imbalanced-learn  
- Jupyter Notebook for analysis and modeling  
- Optional: Power BI / Tableau for visual dashboards  

---

## Future Directions

- Include customer support interactions and Net Promoter Score (NPS) for better predictions.  
- Explore advanced ML models such as LightGBM or CatBoost.  
- Develop a real-time API for churn scoring in CRM systems.  
- Perform cohort analysis to track retention trends over time.

---

## References

- Internal dataset (customer subscription and usage data)  
- Industry best practices on customer retention and churn analysis  
