# Sales_Cohort_Analysis
# Cohort Analysis – Online Retail Dataset (2010–2011)

### Tools Used  
![Python](https://img.shields.io/badge/Python-blue)

### Project Type  
![Data Cleaning](https://img.shields.io/badge/Data%20Cleaning-orange)
![Data Analysis](https://img.shields.io/badge/%20Data%20Analysis-orange)
![Data Visualization](https://img.shields.io/badge/Data%20Visualization-orange)

### Role  
![Stakeholder](https://img.shields.io/badge/Stakeholder-green)

## Table of Contents
1. [Project Background](#1-project-background)  
2. [Project Objectives](#2-project-objectives)  
3. [Data Structure Overview](#3-data-structure-overview)  
4. [Executive Summary](#4-executive-summary)  
5. [Insights Deep Dive](#5-insights-deep-dive)  
6. [Recommendations](#6-recommendations)  
7. [Technical Details](#7-technical-details)  
8. [Assumptions & Caveats](#8-assumptions--caveats)

## 1. Project Background

### Context  
Cohort analysis is a powerful technique for understanding how customer behaviour evolves over time and for identifying performance differences between acquisition periods. In an online retail environment, it allows the business to monitor retention, analyse purchasing trends, and identify potential opportunities to increase long-term value.

### Stakeholders  
The key project stakeholders include the **Business Strategy** team, the **Marketing & CRM** team, and **Product Owners**, all of whom depend on customer retention insights to evaluate marketing effectiveness and improve customer lifecycle strategies.

### Scope  
This project focuses on online retail transactions occurring between December 2010 and December 2011, and analyses retention and purchasing behaviour on a monthly cohort basis to identify actionable insights around acquisition quality and churn trends.

## 2. Project Objectives

- Evaluate customer retention rates over time using monthly cohorts  
- Identify high-performing vs. low-performing acquisition periods  
- Analyse purchase behaviour within each cohort  
- Translate findings into recommendations for improving retention and acquisition effectiveness

## 3. Data Structure Overview

This project uses a transactional dataset which contains all purchases made at a UK-based online retail shop from **01/12/2010 to 09/12/2011**. The dataset includes **541,909 rows** and **8 attributes**, which consist of both identifiers (e.g., InvoiceNo, CustomerID) and transaction metrics (Quantity, UnitPrice). It is a **multivariate time-series dataset** without missing values in the key analytical fields.  
The source of the dataset is London South Bank University, and it has been widely used in academic research for classification, clustering and customer analytics. Given its sequential nature, the dataset is suitable for retention and cohort analysis.

## 4. Executive Summary

Cohort analysis of over **540,000** online transactions reveals a significant decline in retention rates for customers acquired after early 2011. Cohorts acquired between **December-2010 and February-2011** retained up to **40%** of their customers after six months, whereas cohorts from mid-2011 retained fewer than **20%** beyond the second month.  
Additionally, all cohorts experienced a **sudden drop in December-2011**, indicating a seasonal or external factor affecting customer engagement. Despite decreasing retention rates, we observed that **remaining active customers increase their purchase quantity over time**, suggesting that loyal users are more valuable. These insights highlight opportunities to improve early-stage retention, leverage successful past acquisition strategies and invest in high-value customer engagement.

## 5. Insights Deep Dive

- **High retention in early cohorts (Dec-2010 to Feb-2011)**  
The first cohorts, particularly those in December-2010 and January-2011, retain **30–40%** of customers up to month six. This indicates that early acquisition campaigns attracted more loyal and higher-quality users.

- **Rapid churn after month 3 in 2011 cohorts**  
Starting from March-2011, most cohorts show a sharp decline in retention after the second or third month. For instance, the June-2011 cohort drops from **33%** retention in month 6 to just **10%** in month 7, suggesting faster disengagement.

- **Seasonal retention drop in December-2011 (all cohorts)**  
In December-2011, **all cohorts** exhibit a simultaneous drop in retention. Since this trend occurs across the board, it is likely the result of a seasonal or external factor such as reduced marketing activity, stock issues or holiday-related behaviour.

- **Remaining users purchase more over time**  
Although the number of returning users decreases over time, those who remain tend to purchase more. In early cohorts, the average quantity increases from ~12 units to **18–19 units**, indicating that repeat customers become more valuable as their lifecycle progresses.

- **August-2011 cohort anomaly (low retention, high quantity)**  
While the August-2011 cohort has low retention, the few active users purchase considerably higher volumes, suggesting a small but valuable group of heavy buyers.

## 6. Recommendations

- **Launch retention actions immediately after the first purchase (month 1–2)**  
Since most cohorts show the biggest drop after month 2, retention campaigns such as follow-up emails, coupons or personalised product recommendations should be sent within 30 days of the initial purchase.

- **Replicate the acquisition strategy used in late-2010 / early-2011**  
The best performing cohorts were acquired between December-2010 and February-2011. Reviewing and re-applying the marketing initiatives and targeting criteria used during that period could help attract similar high-quality customers.

- **Build seasonal re-engagement campaigns for December**  
The retention drop in December-2011 affects all cohorts, indicating a seasonal disengagement. End-of-year promotions or tailored holiday offers could mitigate this effect and maintain customer activity during that month.

- **Develop a loyalty / VIP program for high-value repeat customers**  
As the average purchase quantity increases over time, it is important to identify and nurture customers who remain active after 3–4 months. Exclusive discounts, access to new products or personalised offers can help increase their long-term value.

- **Investigate heavy-buyer patterns in the August-2011 cohort**  
The presence of a small but high-value user group in this cohort suggests a specific product or use case. Analysing their purchase behaviour could reveal an opportunity for a more targeted marketing campaign focused on similar profiles.

## 7. Technical Details

The CSV file was imported and cleaned by removing duplicate rows and cancelled invoices (`Invoice` starting with “C”), as well as rows with missing `Customer ID`. The `InvoiceDate` column was converted to datetime and transactions with non-positive quantities or unit prices were removed.  
`CohortMonth` was calculated as the month of each customer’s first purchase, and `CohortIndex` was computed as the number of months between the current transaction and the first purchase date. Retention rates were calculated as the percentage of active customers per month, and heatmaps were created using `matplotlib` and `seaborn` for both retention and average quantity metrics.

## 8. Assumptions & Caveats

- The date of the first recorded transaction is assumed to represent the real starting point of each customer’s lifecycle.  
- External influences such as marketing campaigns or pricing changes could not be explicitly controlled for, as they are not included in the dataset.  
- Seasonal effects are inferred from irregular changes in retention behaviour and would need to be confirmed with additional contextual data (e.g., campaign calendar or stock information).
