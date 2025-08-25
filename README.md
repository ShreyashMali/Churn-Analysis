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

##Power BI Dashboard

## 📊 Overview

This project features an interactive *Customer Churn Analysis Dashboard* built in Microsoft Power BI. The dashboard provides a comprehensive view of customer demographics, subscription details, and financial metrics to identify key factors influencing customer churn. The goal is to enable data-driven decision-making for improving customer retention strategies.

## 🚀 Technologies Used

*   *Data Analysis & Visualization:* Microsoft Power BI
*   *Data Processing:* Power Query (M Language)
*   *Data Modeling:* DAX (Data Analysis Expressions)
*   *Key Metrics Calculated:* Churn Rate, Average Tenure, Average Monthly Charges, Total Revenue.

## 📈 Key Insights

The analysis of the customer base reveals several critical insights:

  Overall Churn Rate: The customer churn rate stands at *26.8%*, indicating a significant portion of the subscriber base is leaving.
    Financial Impact: Churned customers generated a total of *$364.93K* in revenue, highlighting the direct financial impact of attrition.
  
Monthly Spending: The average monthly charge for all customers is *$71.47*. A deeper dive into how this differs between retained and churned customers can reveal pricing sensitivities.
Customer Loyalty: The average customer tenure is *31.44* months. Analyzing tenure against churn can help identify the "at-risk" period for subscribers.
Demographic Analysis: The dashboard allows for filtering by *Gender* (Male/Female) to uncover any trends specific to demographic segments.
Payment Methods: The visualization includes analysis by payment method (e.g., Credit Card, Bank Transfer, Electronic Check), which can indicate if certain payment processes are correlated with higher churn.
Tenure vs. Churn: A combined chart shows the count of customers by their tenure and churn status, helping to pinpoint exactly when customers are most likely to leave.

## 📁 Project Structure


├── Churn_Analysis.pbix          # Main Power BI Desktop file
├── CHURN_ANALYSIS.png           # Exported dashboard overview
└── README.md                    # Project documentation (this file)


## 🔮 How to Use

1.  Download the .pbix file and open it with *Microsoft Power BI Desktop*.
2.  Interact with the dashboard by using the various filters (e.g., Gender, Contract Type, Payment Method).
3.  Hover over charts to see detailed tooltips.
4.  Click on specific data points in one visual to cross-filter the others for deeper analysis.

## ✍ Author

Developed as a data analysis project.

