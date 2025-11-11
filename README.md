
# 🏗️ SQL Data Warehouse Project – Medallion Architecture

This project demonstrates the **end-to-end Data Warehousing workflow** designed and implemented in **SQL Server Management Studio (SSMS)** using the **Medallion Architecture** — consisting of **Bronze (Raw Data)**, **Silver (Cleaned Data)**, and **Gold (Business-Ready Data)** layers.

---

## 🎯 Project Objective
To extract raw **Sales Data** from multiple source systems (CRM, ERP), perform **data cleaning, validation, and transformation**, and finally deliver **business-ready models** optimized for analytics and reporting.

---

## 🧩 Datasets
📂 **ERP and CRM Tables**  
👉 Download and use the provided datasets to replicate the workflow.  
These contain transactional, customer, and product-level details used across the Medallion layers.

---

## 🧱 Architecture Overview

### 🥉 **Bronze Layer – Ingest (Raw Data)**
- Stores **raw data** as received from source systems (CSV, CRM, ERP).  
- **Loading Methods:**
  - Batch Processing  
  - Full Load  
  - Truncate & Insert  
- **No transformations** — data is stored *as-is* for traceability and audit purposes.

---

### 🥈 **Silver Layer – Clean (Processed Data)**
- Performs key **data quality operations**:
  - Removal of duplicates & nulls  
  - Standardization (dates, currency, formatting)  
  - Validation (keys & domain rules)  
  - Derived Columns & Enrichment  
- Output: **Cleaned and standardized data** ready for integration into the Gold layer.

---

### 🥇 **Gold Layer – Business-Ready Data (Analytics Layer)**
Implements **business logic and dimensional modeling (Star Schema)**.

- Combines cleaned datasets to create:
  - `gold.fact_sales`
  - `gold.dim_customers`
  - `gold.dim_products`
- **Data Transformations:**
  - Aggregations (Total Sales, Revenue by Product, etc.)
  - Business Calculations (`Sales_Amount = Quantity * Price`)
  - Fact-Dimension Relationships  
- Designed for optimal performance in **Power BI**, **Tableau**, and ad-hoc SQL analytics.

---

## 📊 Star Schema Design

**Fact Table**
- `gold.fact_sales` → Stores transactional metrics such as quantity, price, and sales amount.  

**Dimension Tables**
- `gold.dim_customers` → Contains customer demographics and segmentation details.  
- `gold.dim_products` → Includes product hierarchy, category, and cost attributes.  

**Relationships**
fact_sales.customer_key → dim_customers.customer_key
fact_sales.product_key → dim_products.product_key

---

## ✅ Data Quality Checks Implemented
| Check Type | Description |
|-------------|-------------|
| **Null / Blank Check** | Removed or imputed missing values |
| **Duplicate Check** | Ensured unique transaction & product IDs |
| **Format Standardization** | Unified date, currency, and text formats |
| **Referential Integrity** | Validated all foreign key relationships |
| **Consistency Validation** | Verified sales = quantity × price |

---

## 🧠 Key SQL Operations Used
- **Stored Procedures** – Encapsulated ETL logic within SQL Server  
- **Joins & Unions** – Combined CRM and ERP datasets  
- **CTEs (Common Table Expressions)** – Stepwise data transformation  
- **Aggregate Functions** – `SUM()`, `COUNT()`, `AVG()` for business metrics  
- **Constraints & Keys** – Enforced referential integrity  
- **Views** – Created for the final business-ready reporting layer  

---

## 🧰 Tools & Technologies
- **SQL Server Management Studio (SSMS)**
- **T-SQL** (Stored Procedures, Views, Joins, Aggregations)
- **Data Modeling** (Star Schema Design)
- **ETL Concepts** – Bronze / Silver / Gold Data Flow

---

## 📈 Project Outcomes
✅ Designed and implemented a complete **SQL-based Data Warehouse** from scratch.  
✅ Applied comprehensive **data quality and standardization** steps.  
✅ Built an optimized **Star Schema** for business analytics.  
✅ Prepared data for seamless **Power BI** and **ML integrations**.

---

## 🌟 Project Impact
This project demonstrates how **SQL alone** can serve as a powerful tool for building **ETL pipelines**.  
By manually handling ingestion, transformation, and modeling, it showcases **real-world data engineering skills** — delivering **trustworthy and business-ready insights**.

---

## 🖼️ Visual References
- Medallion Architecture (Bronze → Silver → Gold)  
- SQL Data Warehouse Workflow  
- Star Schema Diagram (Fact & Dimension Tables)

---

## 🚀 Future Enhancements
- Automate ETL pipelines with **SSIS** or **Azure Data Factory**  
- Integrate with **Power BI** for interactive sales dashboards  
- Implement **Data Quality Scorecards** and error tracking mechanisms  

---

## 👩‍💻 Author
**Sneha Busi**  
*Data Analyst | SQL | Power BI | Data Modeling | Machine Learning*  

📬 **Connect with me on LinkedIn:**  
[linkedin.com/in/sneha1631](https://www.linkedin.com/in/sneha1631/)

---



