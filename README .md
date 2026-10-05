# Task 3: Deep-Dive Analysis & Interactive Dashboarding

## Project Overview

This repository contains the end-to-end deliverables for **Task 3: Deep-Dive Analysis & Interactive Dashboarding** during the Data Analytics Internship at **ApexPlanet Software Pvt. Ltd.**

The objective of this project is to perform a multi-dimensional customer segmentation analysis using Python-driven RFM modeling and translate behavioral findings into an interactive executive Power BI dashboard.

---

## 📊 Interactive Dashboard Access & Visual Preview

### 📥 Power BI File Download

- 👉 **[Download Power BI Dashboard File (.pbix)](./Task%203%20Interactive%20Dashboard.pbix)**  
  _(Download and open directly in Power BI Desktop to explore all interactive slicers and cross-filtering)_

### 🖼️ Executive Dashboard Preview

![Executive Customer Segmentation Dashboard](./dashboard_preview.png)

---

## 1. Core KPIs & Business Rationale

| KPI Name                      | Formula                                            | DAX Expression                               | Business Rationale                                                          |
| :---------------------------- | :------------------------------------------------- | :------------------------------------------- | :-------------------------------------------------------------------------- |
| **Total Revenue**             | $\sum(\text{Total Sales})$                         | `SUM(task3_enriched_dataset[Total_Sales])`   | Measures top-line sales turnover and overall business scale.                |
| **Total Orders**              | $\text{Count of Transactions}$                     | `COUNTROWS(task3_enriched_dataset)`          | Tracks order volume and operational purchasing activity.                    |
| **Average Order Value (AOV)** | $\frac{\text{Total Revenue}}{\text{Total Orders}}$ | `DIVIDE([Total Revenue], [Total Orders], 0)` | Evaluates consumer spending power per basket to guide upselling strategies. |
| **Repeat Customer Value**     | $\sum(\text{Sales per Customer})$                  | `CALCULATE([Total Revenue], ALLEXCEPT(...))` | Assesses revenue concentration among high-frequency and VIP buyers.         |

---

## 2. Customer Segmentation (RFM Analysis)

Using Python (`pandas`), an RFM analysis was executed to categorize buyers based on historical engagement:

- **Recency (R):** Days elapsed since the customer's latest transaction relative to the maximum dataset date.
- **Frequency (F):** Total order count per unique customer.
- **Monetary (M):** Cumulative expenditure per customer.

### Customer Cohorts:

1. **Champions (VIP):** Highly engaged recent buyers with superior spending power. Recommended for exclusive VIP loyalty tiers, concierge support, and early product access.
2. **Loyal Spenders:** Consistent repeat spenders who form steady baseline cash flow. Recommended for cross-selling bundles and subscription models.
3. **Potential Regulars:** Moderate transaction value buyers with recent orders. Target candidates for volume-based promotional incentives.
4. **At Risk / Churn Risk:** High or moderate spenders who have not transacted recently. Targeted win-back discounts and re-engagement campaigns are recommended.

---

## 3. Interactive Power BI Dashboard Architecture

- **Executive KPI Cards:** Instant metrics for Total Revenue, Total Volume of Orders, and Average Order Value (AOV).
- **Segment Slicer (Button/Tile Style):** Enables single-click cross-filtering across the entire canvas for any customer cohort.
- **Revenue by Customer Segment (Donut Chart):** Visualizes the revenue share of each customer tier.
- **Product Turnover (Clustered Bar Chart):** Ranks products by revenue contribution across segments.
- **Monthly Revenue Trajectory (Line Chart):** Maps demand peaks and recurring seasonality patterns.
- **Geographical Breakdown (Column Chart):** Highlights city-level revenue distribution.

---

## 4. Repository Structure

```text
├── Task 3 Interactive Dashboard.pbix # Complete Power BI report file
├── cleaned_dataset.csv             # Cleaned transactional data
├── task3_enriched_dataset.csv      # RFM-enriched dataset with segments
├── Task3.ipynb                     # Python RFM analysis and segmentation script
├── dashboard_preview.png           # Dashboard visual snapshot
└── README.md                       # Comprehensive documentation


👤 Author
Rishi Muni
Data Analytics Intern | ApexPlanet Software Pvt. Ltd.
```
