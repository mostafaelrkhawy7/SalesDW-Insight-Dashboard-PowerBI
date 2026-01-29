# Sales Analytics Dashboard (Power BI)

## Project Overview
This project presents an interactive **Sales Analytics Dashboard** built using **Power BI**, powered by a structured **Sales Data Warehouse (Star Schema)**.

The dashboard is designed to support:
- Sales performance monitoring
- Trend and growth analysis
- Profitability and discount risk evaluation

---

## Data Source & Model
- **Source:** SQL Server Data Warehouse (SalesDWH)
- **Model Type:** Star Schema
- **Fact Table:** FactSales
- **Dimensions:** Product, Customer, Location, Ship Mode, Date

The data model follows best practices with **one-to-many relationships** from dimensions to the fact table, ensuring accurate aggregations and scalable analytics.

---

## Date & Time Intelligence
A **custom Calendar table** was created using **DAX** to enable advanced time-based analysis.

### Calendar Logic:
- Dynamic date range from **2014 to 2017**
- Custom DateKey (YYYYMMDD)
- Year, Month Number, Month Name
- Month-Year format
- Quarter labeling (Q1–Q4)

This calendar supports:
- Year-over-Year (YOY) comparison
- YTD calculations
- Seasonal trend analysis

---

## Data Preparation & Modeling
Using **Power Query (M)**:
- Location field was split into **Country** and **City** for better geographic insights
- An **Unknown Product** record was added to handle missing product references
- Null product keys in the fact table were replaced with `-1` to preserve referential integrity
- Redundant relational columns were removed to optimize the semantic model

---

## Key Measures & KPIs (DAX)
The model includes multiple **business-focused DAX measures**, such as:

- Total Sales
- Total Profit
- Total Cost
- Total Quantity
- Sales YTD
- Sales Last Year (LY)
- YOY Growth %
- Average Discount Rate
- Profit Margin %
- Average Order Value
- Risk Sales %
- Discount–Profit Risk Classification

These measures enable both high-level performance tracking and deep profitability analysis.

---

## Dashboard Pages & Insights

### 1️⃣ Sales Dashboard
**Purpose:** Overall business performance snapshot.

**Insights:**
- Total sales exceeded **2.3M**, generating **286K profit**, with margin sensitivity to discounting.
- **Technology** leads in sales contribution, followed by Furniture and Office Supplies.
- The **Consumer segment** contributes the majority of revenue.
- The **West region** dominates sales but also incurs the highest shipping costs.
- Presence of “Unknown” products highlights data quality and master data governance impact.

---

### 2️⃣ Sales Trend
**Purpose:** Time-based performance analysis.

**Insights:**
- Overall **YOY growth reached ~47%**, indicating strong business expansion.
- Sales exhibit clear **seasonality**, with peaks toward the end of the year.
- Monthly volatility suggests reliance on promotions or large orders.
- YTD tracking supports early performance evaluation against historical trends.

---

### 3️⃣ Profitability Risk
**Purpose:** Identify margin erosion caused by discount strategies.

**Risk Classification Logic:**
- Based on **Average Discount Rate** vs **Profit Margin %**
- Categories include:
  - Healthy
  - Low Margin
  - High Discount (Aggressive)
  - High Discount + Low Profit (Risk)

**Insights:**
- Several high-sales products operate at **low or negative margins** due to aggressive discounting.
- High discounts do not always translate into higher profitability.
- “Healthy” products maintain controlled discounts with sustainable margins.
- Pricing optimization opportunities exist to protect overall profitability.

---

## Key Business Takeaways
- Revenue growth is strong, but profitability is highly sensitive to discount policies.
- Discount governance is critical for margin protection.
- Geographic performance should balance demand growth with logistics cost control.
- Data quality improvements directly enhance analytical accuracy.

---

## Tools & Technologies
- Power BI
- DAX
- Power Query (M Language)
- SQL Server Data Warehouse
- Star Schema Data Modeling

---

## Author
**Mostafa Elrkhawy**
