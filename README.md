# 📊 Zara India – Sales & Performance BI Project

## 📌 Project Overview
This project was created to practice and demonstrate core Business Intelligence (BI) skills using PostgreSQL, SQL, and Power BI.  
It is based on a realistic retail scenario for a fashion company (Zara India), where raw data is structured and analyzed to answer common business questions.

The main goal of the project is to show how sales-related data can be transformed into clear, meaningful insights that can be used by business and management teams.

---

## 🖼️ Dashboard Preview

![Overview](screenshots/overview.png)

---

## 🏢 Business Context
Retail companies generate data from many different sources such as sales transactions, customer information, products, inventory, and returns.  
When this data is not properly organized, it becomes difficult to analyze performance or identify trends.

This project simulates a real business situation where:
- Sales performance needs to be tracked over time  
- Store and channel performance must be compared  
- Product-level insight is required  
- Returns and profitability need to be monitored  

---

## 🗂️ Datasets
The project uses synthetic but realistic datasets designed to represent how retail data typically looks in real systems.

### Datasets included:
- **Sales** – Transaction-level sales data  
- **Customers** – Customer details and loyalty information  
- **Products** – Product catalog with pricing and cost data  
- **Inventory** – Store-level inventory snapshots  
- **Returns** – Returned items linked to original sales  

The datasets contain more than 10,000 records in total, which allows meaningful analysis without being unnecessarily complex.

> **Note:** All datasets are artificially generated and used only for learning and portfolio purposes.

---

## 🏗️ Data Architecture

The project follows a simple and realistic BI architecture commonly used in analytics projects.

### 1️⃣ Staging Layer
- Raw CSV files are loaded into staging tables in PostgreSQL.
- These tables closely match the original data structure and act as an intermediate layer.

### 2️⃣ Data Warehouse Layer (Star Schema)
A star schema was created to support analysis and reporting.

**Fact Tables**
- `fact_sales`
- `fact_inventory`
- `fact_returns`

**Dimension Tables**
- `dim_customers`
- `dim_products`
- `dim_stores`
- `dim_dates`

This structure makes it easier to aggregate data and build dashboards efficiently in Power BI.

### 3️⃣ KPI / Reporting Layer
SQL views were created on top of the warehouse tables to calculate key business metrics.  
These views are directly used in Power BI so that business logic stays consistent and centralized in the database.

---

## 📐 Data Modeling Approach
A star schema was chosen because it is widely used in BI and analytics systems.

Key design considerations:
- Fact tables store measurable business data  
- Dimension tables provide descriptive context  
- A separate date dimension supports time-based analysis  
- Clear separation between raw data and analytical data  

This model makes the data easier to understand, query, and visualize.

---

## 📊 Key Business KPIs

Some of the main KPIs calculated using SQL views include:

- Total Revenue  
- Total Orders  
- Units Sold  
- Return Rate (%)  
- Gross Margin (%)  
- Revenue by Store and Sales Channel  
- Top Products by Revenue  
- Monthly Revenue Trend  

KPI logic is implemented in PostgreSQL views (see `sql/kpi_views.sql`), and consumed directly in Power BI.

---

## 📈 Power BI Dashboard

The Power BI report is designed as a single-page executive dashboard.

### Main elements:

#### 🔹 KPI Cards
![KPI Cards](images/kpi_cards.png)

- Total Revenue (₹)  
- Total Orders  
- Units Sold  
- Return Rate (%)  
- Gross Margin (%)  

These give a quick snapshot of overall performance.

#### 🔹 Monthly Revenue Trend
![Monthly Revenue Trend](images/monthly_revenue_trend.png)

A line chart shows how revenue changes across months and years.

#### 🔹 Store & Channel Performance
![Store and Channel Performance](images/store_channel_chart.png)

A bar chart compares performance across stores and separates revenue by sales channel (Store vs Online).

Additional elements:
- Top products table (ranked by revenue)  
- Slicers for store, product category, and year  

The dashboard is intentionally kept simple, focusing on clarity and correctness rather than excessive visuals.

---

## 🛠️ Tools & Technologies

- **PostgreSQL** – Database and analytical data storage  
- **SQL** – Data modeling, transformations, and KPI logic  
- **Power BI Desktop** – Visualization and reporting  
