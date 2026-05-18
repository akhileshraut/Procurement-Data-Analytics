# Procurement Data Analytics Dashboard

## Overview

The Procurement Data Analytics Dashboard is an interactive business intelligence solution built in Power BI to analyze procurement operations, supplier performance, compliance, delivery efficiency, and spending behavior from 2022 to 2024.

This project was designed to help procurement teams and business stakeholders monitor procurement KPIs, evaluate supplier reliability, identify compliance issues, and uncover cost optimization opportunities using dynamic and insight-driven analytics.

---

# Project Objective

The primary objective of this dashboard is to:

* Analyze procurement spend trends over time
* Monitor supplier performance and delivery efficiency
* Evaluate procurement compliance and maverick spend
* Compare procurement spend against budgets
* Identify procurement savings opportunities
* Track supplier risks, tiers, and operational status
* Provide executive-level procurement insights using interactive visual storytelling

---

# Dataset Information

The dataset contains procurement activity from:

* 2022
* 2023
* 2024

### Total Records

* 5,200 Procurement Transactions

### Dataset Includes

* Purchase Orders
* Supplier Information
* Contracts
* Delivery Performance
* Procurement Budgets
* Savings Metrics
* Invoice & Payment Status
* Compliance Information
* Supplier ESG Scores

---

# Dashboard Pages

## Page 1 — Executive Procurement Overview

This page provides a high-level overview of procurement performance and operational trends.

### Key Features

* Interactive KPI selector cards
* Procurement spend trend analysis
* Department performance analysis
* Category & subcategory insights
* PO type distribution
* PO status monitoring
* Dynamic insight subtitles
* Year-wise analysis

### KPIs Included

* Total Spend
* Savings %
* On-Time Delivery %
* Maverick Spend %

---

## Page 2 — Supplier & Compliance Deep-Dive

This page focuses on supplier intelligence, delivery analysis, procurement compliance, and supplier segmentation.

### Key Features

* Supplier performance analysis
* Delivery status segmentation
* Supplier risk analysis
* Regional supplier distribution
* Supplier tier analysis
* Preferred supplier analysis
* Supplier tooltip intelligence cards
* Dynamic KPI interactions

### KPIs Included

* Total Spend
* On-Time Delivery %
* Avg Lead Time
* Preferred Supplier %
* Savings %

---

## Supplier Intelligence Drillthrough

A dedicated drillthrough experience allowing detailed supplier-level operational analysis.

### Includes

* Supplier profile
* Supplier logo
* KPI summary
* Monthly spend trends
* Delivery analysis
* Procurement transaction details
* Compliance indicators

---

# Data Model

The dashboard follows a star schema data model.

## Fact Table

### Fact_Procurement

Contains all procurement transaction-level data.

---

## Dimension Tables

### Dim_Date

Used for time intelligence and trend analysis.

### Dim_Supplier

Contains supplier master information including:

* Supplier Name
* Region
* Country
* Risk
* Tier
* ESG Score
* Preferred Supplier

### Dim_Department

Contains department-level procurement information.

### Dim_Category

Contains procurement category and subcategory information.

---

# Key Metrics & Definitions

## Total Spend

Total procurement expenditure after discounts and before tax.

```DAX
Total Spend =
SUM(Fact_Procurement[Line Net])
```

---

## Savings %

Percentage reduction achieved between budgeted and actual procurement cost.

```DAX
Savings % =
DIVIDE(
    SUM(Fact_Procurement[Savings Amount]),
    SUM(Fact_Procurement[Budget Total]),
    0
)
```

---

## On-Time Delivery %

Percentage of orders delivered on or before the requested delivery date.

```DAX
On-Time Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Fact_Procurement),
        Fact_Procurement[On Time Delivery] = "Yes"
    ),
    COUNTROWS(Fact_Procurement),
    0
)
```

---

## Maverick Spend %

Percentage of procurement spend outside approved procurement channels.

```DAX
Maverick Spend % =
DIVIDE(
    CALCULATE(
        [Total Spend],
        Fact_Procurement[Maverick Spend] = "Yes"
    ),
    [Total Spend],
    0
)
```

---

## Avg Lead Time

Average number of days between purchase order creation and delivery.

```DAX
Avg Lead Time =
AVERAGE(Fact_Procurement[Lead Time Days])
```

---

# Advanced Features Implemented

## Dynamic KPI Selection

Field parameters were used to dynamically switch KPI analysis across visuals.

---

## Dynamic Insight Subtitles

Custom DAX measures generate insight-driven subtitles dynamically based on:

* Selected KPI
* Top category
* Top department
* Top supplier
* Regional performance

---

## Supplier Intelligence Tooltips

Custom tooltip pages provide:

* Supplier logos
* KPI summaries
* ESG scores
* Delivery performance
* Supplier attributes

---

## Delivery Status Segmentation

Procurement deliveries were categorized into:

* Early Delivery
* Slight Delay
* Moderate Delay
* Extreme Delay

---

## Drillthrough Navigation

Supplier-level drillthrough navigation enables detailed procurement investigation.

---

# Design & Theme

## Dashboard Theme

| Element           | Color   |
| ----------------- | ------- |
| Background        | #091017 |
| Visual Containers | #101820 |
| Primary Accent    | #F2BC33 |
| Secondary Accent  | #D6A62A |
| Main Text         | #FCFCFA |
| Secondary Text    | #ABAAA5 |

---

# Tools & Technologies

* Power BI
* Power Query
* DAX
* Data Modeling
* Field Parameters
* Drillthrough Navigation
* Custom Tooltips

---

# Key Business Insights

The dashboard helps stakeholders:

* Monitor procurement spend trends
* Identify high-risk suppliers
* Track procurement savings
* Improve supplier performance visibility
* Reduce procurement delays
* Monitor compliance and maverick spend
* Evaluate supplier delivery reliability
* Support procurement governance initiatives

---

# Learning Outcomes

Through this project, the following skills were applied:

* Advanced Power BI dashboard design
* Data modeling using star schema
* Dynamic DAX calculations
* Interactive visual storytelling
* Procurement analytics
* UX-focused dashboard development
* Drillthrough and tooltip navigation
* KPI-driven reporting architecture

---

# Dashboard Highlights

✔ Executive-level procurement overview

✔ Interactive KPI-driven navigation

✔ Dynamic analytical storytelling

✔ Supplier intelligence tooltips

✔ Procurement compliance monitoring

✔ Premium dark enterprise dashboard theme

✔ Dynamic insight subtitles

✔ Drillthrough supplier analysis

---

# Future Enhancements

Potential future improvements include:

* AI-powered procurement forecasting
* Supplier risk prediction
* Inventory optimization analytics
* Real-time procurement monitoring
* Automated procurement alerts
* Advanced contract analytics

---

# Author

Akhilesh Raut

Data Analyst | Power BI Developer | Procurement Analytics Enthusiast

---

# Dashboard Preview

## Page 1 — Executive Procurement Overview

Add your Page 1 dashboard screenshot here.

```text
Example:
![Page 1 Dashboard](images/page1.png)
```

---

## Page 2 — Supplier & Compliance Deep-Dive

Add your Page 2 dashboard screenshot here.

```text
Example:
Images/page1.PNG
```

---

# YouTube Walkthrough

Add your Power BI dashboard walkthrough or demo video link here.

```text
Example:
https://www.youtube.com/watch?v=YOUR_VIDEO_LINK
```

---

# Connect

If you found this project helpful, feel free to connect and share feedback.
