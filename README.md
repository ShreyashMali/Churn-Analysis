# Churn-Analysis
SQL

## Churn Analysis (SQL)

## Overview

This project analyzes customer churn data using SQL queries to identify churn patterns, customer segments at risk, and key factors influencing retention. The goal is to help businesses improve customer loyalty and reduce churn rates.

## Objectives

 Calculate the total number of churned customers.
 Compare average monthly charges for churned vs. non-churned customers.
 Analyze churn rate by gender.
 Identify high-risk customers with high monthly charges and low tenure.

## Dataset

* Table: `churn_data`
* Key Columns: `CustomerID`, `Churn`, `Gender`, `Age`, `Tenure`, `MonthlyCharges`

## Key SQL Queries

1. **Total Churned Customers**

   ```sql
   SELECT COUNT(*) AS Churned_Customers 
   FROM churn_data 
   WHERE Churn = 'Yes';
   ```

2. **Average Monthly Charges by Churn**

   ```sql
   SELECT Churn, AVG(MonthlyCharges) AS Avg_Monthly_Charges 
   FROM churn_data 
   GROUP BY Churn;
   ```

3. **Churn Rate by Gender**

   ```sql
   SELECT Gender, COUNT(*) AS Total_Customers,
          SUM(CASE WHEN Churn = 'Yes' THEN 1 ELSE 0 END) AS Churned_Customers,
          (SUM(CASE WHEN Churn = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*)) AS Churn_Rate
   FROM churn_data 
   GROUP BY Gender;
   ```

4. High-Risk Customers (High Charges + Low Tenure)

   ```sql
   SELECT CustomerID, Age, MonthlyCharges, Tenure 
   FROM churn_data 
   WHERE MonthlyCharges > 80 AND Tenure < 12;
   ```

## Tools & Technologies

SQL(queries for data exploration and analysis)
Dataset: churn_data.csv

## Insights

Higher monthly charges correlate with higher churn.
 Customers with **low tenure and high bills** are most at risk.
 Gender-based churn patterns can help in targeted retention strategies.

## Purpose

The analysis provides actionable insights for businesses to:

Reduce churn by addressing high-risk customer segments.
Develop targeted pricing and retention strategies.
Improve customer satisfaction and loyalty.
-



# Churn Analysis Dashboard (Power BI)

## Overview

This project uses Power BI to create an interactive dashboard that visualizes customer churn data. The dashboard highlights churn rates, customer demographics, and billing patterns to help businesses identify at-risk customers and improve retention strategies.

## Key Features

1. Overall Churn Rate – Track the percentage of customers who left vs. retained.
2. Demographic Insights – Analyze churn distribution by gender, age group, and tenure.
3. Revenue Impact – Compare average monthly charges for churned vs. active customers.
4. High-Risk Segments– Identify customers with high monthly charges and low tenure.
5. Interactive Filters – Explore churn data across multiple dimensions (tenure, services used, payment method).

## Tools & Technologies

Power BI→ Dashboard creation & data visualization
Dataset → churn_data.csv (CustomerID, Gender, Age, Tenure, MonthlyCharges, Churn)

## Insights

Customers with higher monthly charges and shorter tenure are more likely to churn.
Churn behavior differs across demographics, showing patterns by gender and age.
Interactive filters allow deeper exploration of at-risk customer segments.

## Purpose

This dashboard empowers stakeholders to:

 Monitor churn trends in real time.
 Identify customer segments at high risk of churn.
 Support **data-driven retention strategies** to improve customer loyalty.
