# E-Commerce-Project
A strategic data science project investigating a ~95% checkout funnel drop-off in e-commerce. Features deep-dive funnel analysis, hypothesis testing (SQL/Python), and RFM customer segmentation to pinpoint systemic conversion anomalies


# Strategic Analysis of E-Commerce Conversion Anomalies

This repository contains a comprehensive data-driven investigation into a significant **~95% drop-off rate** observed in the checkout funnel of an e-commerce platform. The analysis focuses on identifying whether this abandonment is driven by user behavior, pricing strategies, or systemic technical failures.

## 🎯 Project Objective
The primary goal is to pinpoint the specific bottleneck preventing users who add items to their carts from completing a purchase. The analysis covers data from **January 2020 to May 2025**, encompassing customer demographics, web traffic, and order details.

## 🛠️ Tech Stack & Tools
* **Data Manipulation:** [Pandas](https://pandas.pydata.org/), [NumPy](https://numpy.org/)
* **Database Operations:** [SQLite3](https://docs.python.org/3/library/sqlite3.html) (In-memory SQL environment)
* **Visualization:** [Matplotlib](https://matplotlib.org/), [Seaborn](https://seaborn.pydata.org/)
* **Statistical Analysis:** [SciPy](https://scipy.org/) (Chi-Squared Testing)
* **Machine Learning:** [Scikit-learn](https://scikit-learn.org/stable/) (K-Means Clustering for RFM Segmentation)

## 🔍 Methodology & Hypothesis Testing
The project systematically evaluates several common e-commerce hypotheses:
1.  **Price Sensitivity:** Do high-value carts convert at lower rates?
2.  **Shipping Thresholds:** Are users abandoning due to shipping costs?
3.  **Trust & Social Proof:** Is there a conversion gap between new and returning customers?
4.  **Device Friction:** Does the mobile experience have higher technical barriers?

## 📈 Key Findings: The "Flatline" Anomaly
The analysis revealed a highly unusual **consistent conversion rate of ~4.4%** across all tested segments (price, country, device, and user type). 
* **Systemic Issue:** The lack of natural variance suggests the bottleneck is a **systemic constant**, such as a payment gateway failure or a functional bug in the checkout API.
* **RFM Segmentation:** Customers were successfully segmented into 'Loyal', 'At Risk', 'Champions', and 'Low Value' groups using K-Means clustering, yet even high-value segments faced the same conversion ceiling.

## 📂 Project Structure
* `E_commerce_data.ipynb`: The primary analysis notebook containing SQL queries and Python visualizations.
* `Tableau_Sessions.csv`: Exported session-level data with added `user_type` and `Segment_Name` for BI reporting.
* `Tableau_RFM.csv`: Detailed customer segmentation data for scatter plot analysis.

## 🚀 Recommended Action Plan
Based on the results, a **high-priority technical audit** is recommended:
1.  **Engineering Ticket:** Investigate 500/400 errors in the `/pay` API calls.
2.  **QA Testing:** Simulate "Guest Checkout" flows to find session-based errors.
3.  **Third-Party Audit:** Ensure no scripts are blocking the "Submit Order" button.
