# Revenue Metrics

## Overview

**Revenue Metrics** is a final Data Analytics course project focused on
analyzing revenue dynamics and user payment behavior in a
subscription-based product.

The dashboard is designed for product managers to monitor changes in
revenue and paid users over time and identify the main factors driving
these changes.

The analysis covers recurring revenue, paid users, user acquisition and
churn, revenue expansion/contraction, ARPPU, and customer lifetime
metrics.

## Objectives

-   Track monthly revenue dynamics and Monthly Recurring Revenue (MRR).
-   Monitor the number of Paid Users and New Paid Users.
-   Analyze ARPPU over time.
-   Identify factors behind changes in revenue and paid users.
-   Analyze customer churn and Churn Rate.
-   Track Churned Revenue and Revenue Churn Rate.
-   Measure Expansion MRR and Contraction MRR.
-   Analyze Customer Lifetime (LT) and Lifetime Value (LTV).
-   Enable segmentation by month, user age group, and language.

## Data Source

The project uses data from a PostgreSQL database.

Main source tables used in the analysis:

-   `project.games_payments` --- payment transactions and revenue
    amounts.
-   `games_paid_users` --- user attributes used for dashboard
    segmentation.

The SQL transformation aggregates payments by user and calendar month
and calculates the fields required for churn, expansion, and contraction
analysis.

## Tools

-   **PostgreSQL** --- data preparation and metric calculations
-   **DBeaver** --- SQL development
-   **Tableau** --- data visualization and dashboard development
-   **Git / GitHub** --- project version control and portfolio
    presentation

## Data Preparation

The SQL workflow is based on several CTEs:

1.  **`monthly_revenue`**\
    Aggregates revenue for each user by calendar month.

2.  **`calculated_months`**\
    Adds previous/next calendar months and previous/next paid months
    using window functions.

3.  **`calculated_metrics`**\
    Calculates:

    -   Churn Month
    -   Churned Revenue
    -   Churned Users
    -   Expansion MRR
    -   Contraction MRR

4.  **Final dataset**\
    Joins the calculated payment metrics with user attributes such as
    age, game, language, and device information.

## Dashboard

The Tableau dashboard contains five main analytical views:

### 1. Revenue Movement by Month

Shows the main components of monthly revenue movement:

-   MRR
-   New MRR
-   Expansion MRR
-   Contraction MRR
-   Churned Revenue

This view helps identify the main drivers behind changes in recurring
revenue.

### 2. Users Movement by Month

Shows the movement of the paid-user base:

-   New Paid Users
-   Churned Users

The view makes it possible to compare user acquisition and churn
dynamics month by month.

### 3. Paid Users & ARPPU Over Time

Tracks:

-   Paid Users
-   ARPPU

This view shows how the size of the paying customer base changes
together with average revenue per paid user.

### 4. Churn Rate by Age Group

A heatmap showing monthly Churn Rate across user age groups.

It allows product managers to identify age segments with relatively
higher or lower churn.

### 5. LTV & LT by Month

Compares:

-   Customer Lifetime Value (LTV)
-   Customer Lifetime (LT)

This view provides a high-level perspective on customer value and the
duration of customer relationships.

## Filters

The dashboard includes filters for:

-   Month
-   Age Group
-   Language

## Key Analytical Focus

The dashboard is designed around two main questions:

**What is changing?**\
Revenue, paid users, ARPPU, churn, LTV, and LT are tracked over time.

**Why is it changing?**\
Revenue movement is decomposed into New MRR, Expansion MRR, Contraction
MRR, and Churned Revenue, while paid-user movement is decomposed into
New Paid Users and Churned Users.

## Project Structure

``` text
Revenue-metrics/
│
├── sql/
│   └── Revenue_metrics_Afanasonok_FP.sql
│
├── tableau/
│   └── Revenue_metrics_Afanasonok_FP.twb
│
├── screenshots/
│   └── dashboard.png
│
└── README.md
```

## Disclaimer

This project was created as a final project for a Data Analytics course.
The dashboard and analysis are intended for educational and portfolio
purposes.
