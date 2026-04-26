# ☕ Coffee Shop Sales Dashboard | Power BI

## 📋 Project Overview

An end-to-end Power BI dashboard analyzing sales performance 
of Maven Coffee Shop across 3 New York City locations.

**Stakeholder:** Sarah Mitchell, Regional Operations Manager  
**Business Question:** Which stores and products drive revenue, 
and how is performance trending over time?

---

## 📊 Dashboard Pages

| Page | Description |
|------|-------------|
| Cover | Project overview, key findings, stakeholder context, navigation |
| Store Performance | KPI cards, revenue by store, top 5 categories, weekday trends, dynamic slicers |
| Product & Time Analysis | Monthly revenue trend, revenue by category matrix, top 5 products, cumulative growth |
| Product Detail | Drillthrough page — full category breakdown with KPIs, monthly trend, product type table |
| Tooltip — Store | Custom hover tooltip showing Revenue and Transactions on bar chart |

---

## 💡 Key Findings

- ☕ Coffee drives **41.45%** of total revenue ($105K)
- 🏪 Hell's Kitchen is top store at **$93K** revenue
- 📅 **Monday & Wednesday** are peak transaction days
- 📉 Revenue shows declining trend **post-August**
- 🏆 Top 5 products account for **80%+** of total sales
- 💰 Cumulative revenue crossed **$264K** in 2023

---

## 🗂️ Dataset

| Detail | Info |
|--------|------|
| Source | Maven Analytics (Free) |
| Original Size | 149,116 rows |
| Clean Size | 58,202 rows |
| Removed | 90,914 rows (unrecoverable date errors) |
| Period | January 2023 — December 2023 |
| Columns | 11 (Transaction ID, Date, Time, Store, Product, etc.) |

---

## 🛠️ Tools & Techniques

**Tools:** Power BI Desktop | DAX | Power Query

**Techniques Used:**
- Data cleaning — date format fix, type corrections
- Star Schema modelling — 5 tables, 4 relationships
- DAX — CALCULATE, FILTER, RANKX, TOTALYTD,
  DATESINPERIOD, SWITCH, VAR/RETURN, SELECTEDVALUE
- Dynamic KPI — metric slicer drives chart + title
- Conditional formatting — green/orange/red revenue cells
- Time Intelligence — YTD, Running Total, Moving Average
- Drillthrough page — right-click any product category to drill into full detail
- Bookmarks & buttons — app-style navigation bar across all pages
- Synced slicers — Quarter and Date Range slicers work across pages
- Custom tooltip page — hover over bar chart to see Revenue + Transactions
- Custom theme — consistent coffee palette applied across all visuals
- Business storytelling — stakeholder persona, key findings, data quality notes

---
![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/1_Cover.png)
![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/2_Store%20Performance.png)
![Dashboard Preview]()
![Dashboard Preview]()
## 📁 File Structure
