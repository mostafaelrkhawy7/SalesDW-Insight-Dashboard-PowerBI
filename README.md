# 📊 Sales Analytics Dashboard (Power BI)

---

## 🔍 Project Overview
This project presents an interactive **Sales Analytics Dashboard** built using **Power BI**, powered by a structured **Sales Data Warehouse (Star Schema)**.

The dashboard is designed to support:
- 📈 Sales performance monitoring  
- 📊 Trend and growth analysis  
- ⚠️ Profitability and discount risk evaluation  

---

## 🗄️ Data Source & Model
| Item | Description |
|-----|------------|
| **Source** | SQL Server Data Warehouse (SalesDWH) |
| **Model Type** | Star Schema |
| **Fact Table** | FactSales |
| **Dimensions** | Product, Customer, Location, Ship Mode, Date |

The model follows best practices using **one-to-many relationships** from dimensions to the fact table to ensure accurate aggregations and scalability.

---

## 🔧 Data Preparation (Power Query – M Language)
Power Query was used to clean, enrich, and prepare the data before modeling.

### Key Transformations:
- 🌍 Split `Location` into **Country** and **City** for geographic analysis
- ❓ Added an **Unknown Product** record to handle missing product references
- 🔗 Replaced null product keys in the fact table with `-1` to preserve referential integrity
- 🧹 Removed unnecessary relational columns to optimize the semantic model

These steps ensure reliable reporting and prevent data loss during analysis.

---

## 🗓️ Date & Time Intelligence (DAX Calendar)
A **custom Calendar table** was created using **DAX** to enable advanced time intelligence.

### Calendar Features:
| Attribute | Description |
|---------|------------|
| Date Range | 2014 – 2017 |
| DateKey | YYYYMMDD format |
| Year | Calendar Year |
| MonthNum | Numeric month |
| MonthName | Month short name |
| Month-Year | MMM-YYYY |
| Quarter | Q1 – Q4 |

This calendar enables:
- 📅 Year-over-Year (YOY) comparisons  
- 📊 Year-To-Date (YTD) calculations  
- 🔁 Seasonal trend analysis  

---

## 📐 Data Modeling
- ⭐ Star Schema with centralized **FactSales**
- 🔑 Surrogate keys used for all dimensions
- ➡️ Single-direction filters from dimensions to fact
- 🧠 Optimized for DAX performance and clarity

---

## 📈 Key Measures & KPIs (DAX)
The dashboard includes business-focused DAX measures such as:

| Category | Measures |
|--------|---------|
| Sales | Total Sales, Sales YTD, Sales LY, YOY Growth % |
| Profitability | Total Profit, Profit Margin %, Total Cost |
| Orders | Total Quantity, Average Order Value |
| Discounts | Avg Discount Rate, Discount Value |
| Risk Analysis | Risk Sales %, Discount–Profit Risk |

These measures allow both high-level monitoring and deep profitability insights.

---

## 📊 Dashboard Pages & Insights

### 🟢 1. Sales Dashboard
**Purpose:** Executive-level overview of business performance.

**Insights:**
- 💰 Total sales exceeded **2.3M**, generating **286K profit**
- 🖥️ **Technology** is the top-selling category
- 👥 **Consumer segment** is the primary revenue driver
- 📍 **West region** leads in sales but also has the highest shipping cost
- ⚠️ Presence of “Unknown” products highlights data quality impact

---

### 🔵 2. Sales Trend
**Purpose:** Analyze performance over time.

**Insights:**
- 📈 Overall **YOY growth ≈ 47%**
- 📆 Clear seasonality with year-end peaks
- 🔄 Monthly volatility suggests reliance on promotions or large orders
- 🎯 YTD tracking supports early performance evaluation

---

### 🔴 3. Profitability Risk
**Purpose:** Detect margin erosion caused by discounting.

#### Risk Classification Logic:
- Avg Discount Rate vs Profit Margin %

| Risk Category | Meaning |
|--------------|--------|
| 🟢 Healthy | Sustainable margin & discount |
| 🟡 Low Margin | Profitable but sensitive |
| 🟠 High Discount (Aggressive) | Requires monitoring |
| 🔴 High Discount + Low Profit | Immediate pricing risk |

**Insights:**
- High discounts often lead to **negative or near-zero margins**
- Aggressive discounting does not guarantee higher profitability
- Pricing optimization can significantly improve margins

---

## 🧠 Key Business Takeaways
- 🚀 Strong revenue growth with margin sensitivity to discounts
- ⚖️ Discount governance is critical for profitability protection
- 🌍 Regional growth must balance logistics cost
- 🧹 Data quality directly affects insight accuracy

---

## 🛠️ Tools & Technologies
| Tool | Purpose |
|----|--------|
| Power BI | Data visualization & modeling |
| DAX | Measures & time intelligence |
| Power Query | Data transformation |
| SQL Server | Data Warehouse |
| Star Schema | Analytical modeling |

---

## ✍️ Author
**Mostafa Elrkhawy**
