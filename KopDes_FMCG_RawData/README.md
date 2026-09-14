# 📊 KopDes FMCG Sales Analytics

A portfolio-grade **Power BI sales and distribution analytics project** built to monitor FMCG performance across sales, products, targets, distributors, outlets, and inventory.

This repository showcases an end-to-end **Power BI Business Intelligence Dashboard** built from data preparation through final dashboard QA.

> **Dataset note:** This project uses a synthetic FMCG sales and distribution dataset covering **January 2025 to December 2026**.

---

## 🎯 Project Objective

The objective of this project is to build an end-to-end analytical solution that can help business users answer questions such as:

- How are sales performing over time?
- Which distributors, channels, regions, and products contribute the most revenue?
- Are sales teams meeting their targets?
- Which products drive most of the business?
- Where are the largest positive or negative sales variances?
- How healthy is inventory across distributors and product categories?
- Which areas require deeper investigation?

The project was built end-to-end, including:

- Data cleaning and transformation
- Data quality checks
- Star-schema data modelling
- DAX measure development
- Time intelligence
- KPI and business-rule validation
- Dashboard design and interaction
- Final report QA

---

## 🗂️ Dataset Overview

The model contains sales, target, inventory, and master data.

### 📌 Main Fact Tables

- **Fact Sales** – transaction-level sales data
- **Fact Target** – monthly sales and active outlet targets
- **Fact Inventory** – monthly inventory snapshots

### 🧩 Main Dimensions

- Date
- Product
- Distributor
- Salesperson
- Outlet

### 📏 Data Scale

- **130,995 sales rows**
- **79,239 unique invoices**
- **4,000 outlets**
- **45 products**
- **18 distributors**
- **48 salespersons**
- **2 years of data: 2025–2026**

---

## 🧱 Data Model

The Power BI semantic model follows a **star / fact constellation schema**.

Key relationships include:

- Date → Sales
- Date → Target
- Date → Inventory
- Product → Sales
- Product → Inventory
- Distributor → Sales
- Distributor → Target
- Distributor → Inventory
- Salesperson → Sales
- Salesperson → Target
- Outlet → Sales

Relationships are configured as **one-to-many**, with filters flowing from dimensions to facts.

This design keeps the model scalable, easy to maintain, and suitable for analytical reporting.

---

## 🧮 Key Measures

The report includes measures for:

### 💰 Sales
- Total Net Sales
- Total Gross Sales
- Total Quantity
- Total Invoices
- Active Outlets
- Average Order Value
- Sales per Active Outlet
- Sales per Active Salesperson

### 📈 Profitability
- Total COGS
- Gross Profit
- Gross Margin %
- Discount Rate %

### 🎯 Target Performance
- Sales Target
- Sales Variance
- Sales Variance %
- Sales Achievement %
- Active Outlet Target
- Outlet Achievement %

### 📦 Inventory
- Closing Stock
- Stock Value
- Average Stock Value
- Inventory Turnover
- Average Monthly Units Sold
- Stock Cover Months

### 🕒 Time Intelligence
- Previous Month Sales
- MoM Growth
- Previous Year Sales
- YoY Growth
- YTD Sales
- YTD Target
- YTD Achievement

### 🛍️ Product Analysis
- Product Sales Rank
- Product Cumulative Sales
- Product Cumulative %
- Pareto 80% Reference

---

# 🖥️ Dashboard Pages

## 1️⃣ Executive Overview

The Executive Overview provides a high-level view of overall business performance.

Main components:

- Net Sales
- Gross Profit
- Gross Margin
- Sales Achievement
- Active Outlets
- Monthly Sales vs Target
- Sales Mix by Category
- Sales Mix by Channel
- Top Distributors
- Distributor Performance Matrix

This page is designed for quick management-level monitoring.

---

## 2️⃣ Sales Performance

The Sales Performance page focuses on sales growth and operational performance.

Main analysis:

- Net Sales
- MoM Growth
- YoY Growth
- Average Order Value
- Total Invoices
- Current Year vs Last Year sales trend
- Sales Growth Momentum
- Region and Channel contribution
- Detailed distributor performance

This page helps identify where sales are growing, slowing down, or underperforming.

---

## 3️⃣ Product Performance

The Product Performance page provides deeper SKU and category analysis.

Main analysis:

- Category Sales & Margin
- Top 10 Products by Net Sales
- Product Pareto Analysis
- Detailed Product Performance Matrix

The Pareto analysis helps identify which products contribute the majority of total sales.

---

## 4️⃣ Target Performance

The Target Performance page focuses on actual sales versus business targets.

Main analysis:

- Sales Achievement %
- Sales Variance
- Monthly Sales Variance to Target
- Distributor Variance to Target
- Salesperson Target Performance

Conditional formatting highlights:

- **Red** = below target
- **Green** = achieved or exceeded target

This page is designed to quickly identify where the largest target gaps are coming from.

---

## 5️⃣ Inventory Performance

The Inventory Performance page monitors current stock position and inventory efficiency.

Main analysis:

- Closing Stock
- Stock Value
- Stock Cover Months
- Monthly Closing Stock Trend
- Closing Stock by Category
- Detailed Distributor → Category → Product inventory analysis

The report uses monthly inventory snapshots to avoid incorrectly aggregating closing stock across time.

---


## 🖼️ Dashboard Preview

> Add exported screenshots to the `screenshots/` folder using the filenames below.

### 🧭 Executive Overview
![Executive Overview](screenshots/overview.png)

### 💰 Sales Performance
![Sales Performance](screenshots/sales-performance.png)

### 🛍️ Product Performance
![Product Performance](screenshots/product-performance.png)

### 🎯 Target Performance
![Target Performance](screenshots/target-performance.png)

### 📦 Inventory Performance
![Inventory Performance](screenshots/inventory-performance.png)

---

## 🎨 Dashboard Design

The report uses a consistent red-and-white corporate design system.

### 🎨 Main Colors

- Primary Red: `#C62828`
- Positive Green: `#2E7D32`
- Dark Text: `#1F2937`
- Secondary Text: `#6B7280`
- Border: `#E5E7EB`
- Background: `#F6F7F9`

The report canvas is designed in **16:9 format** with consistent navigation, KPI cards, visual containers, typography, slicers, and conditional formatting.

---

## ✅ Data Quality & Validation

Before building the final dashboard, multiple QA checks were performed.

Examples include:

- Missing-value checks
- Duplicate-grain validation
- Orphan-key checks
- Data type validation
- Sales formula validation
- Inventory reconciliation
- Target relationship testing
- Date filtering tests
- Distributor filtering tests
- Product filtering tests
- Monthly inventory snapshot validation
- MoM, YoY, and YTD measure validation

A relationship issue found during testing was corrected before final dashboard development, reinforcing the importance of validating model behavior before visualization.

---

## 📝 Project Summary

This project demonstrates the complete workflow of a Data Analyst working with Power BI:

**Raw Data → Cleaning → Data Modelling → DAX → QA → Business Analysis → Dashboard Design**

The final dashboard enables users to monitor the business from multiple perspectives:

- Executive performance
- Sales growth
- Product contribution
- Target achievement
- Inventory efficiency

### 📊 Overall Dataset Performance

Across the full 2025–2026 dataset:

- **Net Sales:** approximately **Rp44.88B**
- **Gross Profit:** approximately **Rp15.96B**
- **Gross Margin:** approximately **35.56%**
- **Quantity Sold:** approximately **4.40M units**
- **Unique Invoices:** **79,239**
- **Active Outlets:** **4,000**

---

## 🛠️ Tools Used

- **Power BI Desktop**
- **Power Query**
- **DAX**
- **Excel / CSV**
- **Git & GitHub**

---

## 📁 Repository Structure

```text
kopdes-fmcg-sales/
│
├── README.md
│
├── dashboard/
│   └── KopDes_FMCG_Sales.pbix
│
└── screenshots/
    ├── overview.png
    ├── sales-performance.png
    ├── product-performance.png
    ├── target-performance.png
    └── inventory-performance.png
```

> If the `.pbix` file is too large for normal GitHub storage, use Git LFS or publish screenshots / a demo video instead.

---

## 👤 Author

**Andi Kahfi**

Power BI Data Analytics Portfolio Project

⭐ If you find this project useful, feel free to explore the repository and connect with me on LinkedIn.
