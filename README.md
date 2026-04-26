# ☕ Coffee Shop Sales Dashboard | Power BI

---

## 📋 Project Overview

Built an end-to-end Power BI dashboard analyzing sales performance of Maven Coffee Shop across 3 New York City locations — Hell's Kitchen, Astoria, and Lower Manhattan. The project covers the full pipeline from raw data cleaning in Power Query to a fully interactive 4-page dashboard with advanced DAX, drillthrough, bookmarks, and dynamic visuals.

**Stakeholder:** Sarah Mitchell, Regional Operations Manager
**Business Question:** Which stores and products drive the most revenue, and how is performance trending over time?

---

## ❓ Problem Statement

The coffee shop needed clarity on its sales performance across stores, products, and time periods. The specific areas analyzed include:

- Total revenue, transactions, and quantity sold
- Revenue performance by store location
- Sales trends across weekdays and months
- Product category and individual product performance
- Revenue distribution — high, medium, and low performing transactions
- Cumulative revenue growth over the full year
- Category-level drillthrough for detailed product breakdown

---

## 📊 Dashboard Pages

| Page | Description |
|------|-------------|
| Cover | Stakeholder context, business question, key findings, data quality notes, tools and skills |
| Store Performance | KPI cards, top 5 by category donut, revenue by store bar chart, weekday revenue line chart, Quarter + Date Range slicers, dynamic metric slicer |
| Product & Time Analysis | Monthly revenue trend, revenue by category × month matrix, top 5 products pie chart, cumulative revenue growth line chart, product category slicer |
| Product Detail | Drillthrough page — KPI cards, monthly revenue trend, product type breakdown table |
| Tooltip — Store | Custom hover tooltip showing Revenue and Total Transactions on bar chart hover |

---

## 🖼️ Visualizations Used

**Cover Page**
- Static text boxes for stakeholder card, business question, key findings, data quality notes, tools and skills demonstrated
- Navigation buttons (bookmarks) linking to Store Performance and Products pages
- Background image with coffee theme overlay

**Slicers & Filters**
- **Quarter Slicer** — Dropdown slicer filtering all visuals on Store Performance page by quarter. Synced across Store Performance and Products pages so selection carries over on navigation.
- **Date Range Slicer** — Between-style date picker allowing custom date range selection. Synced across Store Performance and Products pages.
- **Metric Name Slicer** — Disconnected slicer driving dynamic KPI cards, chart titles, donut chart, bar chart, and line chart on Store Performance page. Options: Revenue, Total Transactions, Total Quantity, Avg Order Value, Avg Revenue Per Item.
- **Product Category Slicer** — Dropdown slicer on Products and Time Analysis page filtering all visuals to a specific product category.
  
**KPI Cards — Store Performance Page**
- 5 cards showing Total Revenue, Total Transactions, Total Quantity, Avg Order Value, Avg Revenue Per Item
- Driven by the **Metric Name slicer** — selecting a metric updates the relevant card highlight and dynamic chart titles across the page

**Donut Chart — Top 5 Product Categories by Metric**
- Shows top 5 product categories based on the selected metric (Revenue / Transactions / Quantity)
- Title updates dynamically based on **Metric Name slicer** selection
- Displays percentage contribution of each category

**Bar Chart — Revenue by Store with Revenue Category**
- Horizontal bar chart comparing all 3 store locations
- Color-coded legend: High / Medium / Low revenue categories using conditional column
- Dynamic title driven by Metric Name slicer

**Line Chart — Weekday Revenue by Store**
- Shows revenue trend across Monday to Sunday
- Helps identify peak and low traffic days across the full week
- Dynamic title updates based on selected metric

**Column Chart — Monthly Revenue Trend**
- Month-by-month revenue bars from January to December
- Shows seasonal pattern — peak in August, decline post-August
- Dynamic title driven by metric slicer on Store Performance page

**Matrix — Revenue by Category × Month**
- Rows: Product Categories | Columns: Months (Jan–Dec)
- Conditional formatting applied — green (high), orange (medium), red (low) revenue cells
- Total row at bottom for quick monthly comparison

**Pie Chart — Top 5 Products by Metric**
- Shows top 5 individual products based on selected metric
- Dynamic title updates with slicer selection
- Percentage labels visible on each slice

**Line Chart — Cumulative Revenue Growth**
- Running total of revenue from January through December
- Shows steady business growth trajectory over the full year
- Useful for understanding overall revenue momentum

**Product Detail — Drillthrough Page**
- Triggered by right-clicking any Product Category or any Product Type across the report
- 5 KPI cards auto-filtered to the drilled category
- Column chart showing monthly revenue trend for that category only
- Table showing Product Type breakdown with Revenue and Total Transactions

**Custom Tooltip Page**
- Appears on hover over the Revenue by Store bar chart
- Shows Revenue and Total Transactions cards in a compact coffee-themed layout
- Replaces the default Power BI tooltip

---

## 💡 Key Findings

- ☕ Coffee drives **41.45%** of total revenue ($105K) — dominant across all 3 stores
- 🏪 Hell's Kitchen leads at **$93K** despite similar store size to others
- 📅 **Monday & Wednesday** are peak days at ~9,200 transactions each
- 📉 Revenue peaked at **$25K in August** and declined steadily to $19K by December
- 🏆 **Barista Espresso** alone contributes 24.77% of product revenue
- 💰 Cumulative revenue crossed **$264K** by December 2023
- 🍵 Within Tea category — **Brewed Chai Tea** leads at $30.8K across 7,096 transactions

---

## 🗂️ Dataset

| Detail | Info |
|--------|------|
| Source | Maven Analytics (Free) |
| Original Size | 149,116 rows |
| Clean Size | 58,202 rows |
| Removed | 90,914 rows (unrecoverable date errors) |
| Period | January 2023 — December 2023 |
| Columns | 11 (Transaction ID, Date, Time, Store, Product, Category, Type, Unit Price, Quantity) |

---

## 🛠️ Tools & Techniques

**Tools:** Power BI Desktop | DAX | Power Query

**Power Query:**
- Fixed mixed-format Date column using locale-based type conversion (English UK)
- Corrected all column data types
- Created Revenue = Unit Price × Quantity custom column
- Extracted Year, Month Name, Day Name, Hour from Date and Time columns
- Added Index column as Row ID
- Created Revenue Category conditional column (High / Medium / Low)
- Built Store_Summary and Product_Summary tables using Group By
- Merged queries for related table lookups

**Data Modelling:**
- Star Schema — 5 tables, 4 one-to-many relationships
- Separate Date Table connected via Date column
- KPI_Measures table for all DAX measures
- Disconnected Metrics table for dynamic slicer

**DAX Measures:**
- CALCULATE, ALL(), ALLEXCEPT(), REMOVEFILTERS()
- TOTALYTD, SAMEPERIODLASTYEAR, DATEADD, DATESINPERIOD
- Running Total, 3-Month Moving Average
- RANKX(), SWITCH TRUE(), FILTER(), RELATED()
- SUMX, AVERAGEX, COUNTX iterator functions
- VAR/RETURN, SELECTEDVALUE(), HASONEVALUE(), ISINSCOPE()
- Dynamic KPI measure driven by Disconnected Metrics slicer

**Dashboard Design:**
- 4-page report with Tooltip and Drillthrough pages
- Bookmarks + buttons for app-style page navigation
- Synced Quarter and Date Range slicers across pages
- Conditional formatting — green/orange/red on matrix
- Dynamic titles driven by Metric Name slicer
- Custom coffee JSON theme — consistent palette across all visuals
- Custom tooltip page on bar chart hover

---

## 💡 Exploratory Questions Answered

- Which store location drives the most revenue and why?
- Which product categories and individual products contribute most to sales?
- How does revenue trend across weekdays — when is peak footfall?
- What is the monthly revenue pattern — is there seasonality?
- How does cumulative revenue grow across the full year?
- Which category products perform best when drilled into detail?

---

## 💬 Recommendations

| # | Recommendation | Detail |
|---|---|---|
| 1 | Investigate Post-August Decline | Revenue fell from $25K to $19K. Review staffing, inventory, and seasonal factors |
| 2 | Double Down on Coffee | At 41.45% of revenue, new variants or promotions here have highest upside |
| 3 | Replicate Hell's Kitchen | Identify what's working there and apply to Astoria and Lower Manhattan |
| 4 | Protect Barista Espresso Stock | 24.77% from one product is a supply risk — maintain consistent stock |
| 5 | Target Peak Days | Monday & Wednesday ~9,200 transactions — loyalty offers could push avg order value |

---

## ⚠️ Data Quality Notes

- Original dataset had mixed date formats across 149,116 rows
- After locale-based conversion in Power Query, 90,914 rows were unrecoverable and removed
- Clean dataset: 58,202 rows — January to December 2023 only
- Single year of data — Year-over-Year comparisons not possible
  
---

![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/1.Cover.png)
![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/2.Store%20Performance.png)
![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/3.Product%20%26%20Time%20Analysis.png)
![Dashboard Preview](https://github.com/BrindaJat/coffee-shop-powerbi/blob/main/screenshots/4.Product%20Detail.png)
## 📁 File Structure
```
coffee-shop-powerbi/
├── 📁 screenshots/
│   ├── 1_Cover.png
│   ├── 2_Store_Performance.png
│   ├── 3_Product_and_Time_Analysis.png
│   └── 4_Product_Detail.png
├── Coffee_Shop_Dashboard.pbix
├── Coffee_Shop_Executive_Summary.pdf
└── README.md
```
