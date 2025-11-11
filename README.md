# SQL_DATA_WARE_HOUSE_PROJECT_MEDALLION_ARCHITECTURE
This project demonstrates the complete data warehousing workflow built in SQL Server Management Studio (SSMS) using the Medallion Architecture — consisting of Bronze (Raw Data), Silver (Cleaned Data), and Gold (Business-Ready Data) layers.

The objective was to take raw sales data from multiple source systems (CRM, ERP), perform data cleaning, validation, and transformation, and finally deliver business-ready data models optimized for analytics and reporting.

DATASETS----> Download the ERP and CRM tables provided here 

🏗️ Architecture Overview
🔸 Bronze Layer – Ingest
Stores raw data as received from sources (CSV files, CRM, ERP).
Data loading through:
Batch Processing
Full Load
Truncate & Insert
No transformations — data is stored as-is for traceability.

🔸 Silver Layer – Clean
Performs:
Data Cleansing (removal of duplicates, null checks)
Standardization (date, currency, and format normalization)
Validation (key integrity and domain constraints)
Derived Columns and Data Enrichment
Output is cleaned and standardized data ready for integration.

🔸 Gold Layer (Business-Ready Data – “Analytics”)
This layer is where the business logic is implemented and the Star Schema is created.Transforms cleaned data into business-ready models.
The purpose is to deliver a single source of truth for analytics, BI, and reporting.
Combines cleaned datasets to create fact and dimension tables:
gold.fact_sales
gold.dim_customers
gold.dim_products

Data transformations in this layer include:
Aggregations and metrics (e.g., total sales, revenue by product)
Business calculations such as Sales_Amount = Quantity * Price
Dimensional modeling using Fact and Dimension tables
Designed for optimal performance in Power BI, Tableau, or ad-hoc SQL analysis.

Star Schema Structure:
gold.fact_sales → Contains transaction-level metrics
gold.dim_customers → Customer demographics
gold.dim_products → Product hierarchy and details

📊 Data Model (Star Schema)
Fact Table:
gold.fact_sales → Stores metrics such as quantity, price, sales amount, and foreign keys linking to dimensions.

Dimension Tables:
gold.dim_customers → Customer details (demographics, marital status, country, etc.)
gold.dim_products → Product details (category, maintenance status, cost, etc.)

Relationships:
fact_sales.customer_key → dim_customers.customer_key
fact_sales.product_key → dim_products.product_key

🔹 Data Quality Checks Implemented
Null and Blank Check-	Removed or imputed missing values
Duplicate Check-	Ensured unique transaction and product IDs
Format Standardization-	Unified date and currency formats
Referential Integrity-	Validated foreign key relationships
Consistency Validation-	Checked that sales amounts align with quantity × price

🔹 Key SQL Operations Used
Stored Procedures for ETL logic within SQL Server
Joins and Unions for dataset merging
CTEs (Common Table Expressions) for stepwise transformation
Aggregate Functions (SUM, COUNT, AVG) for business metrics
Constraints & Keys to maintain referential integrity
Views for exposing final business-ready datasets

🧰 Tools & Technologies
SQL Server Management Studio (SSMS)
T-SQL (Stored Procedures, Views, Joins, Aggregations)
Data Modeling (Star Schema Design)
ETL Concepts – Bronze/Silver/Gold Data Flow

📈 Project Outcomes
✅ Designed and implemented an SQL-based data warehouse from scratch.
✅ Performed complete data quality checks and standardization.
✅ Built a robust star schema for sales analytics.
✅ Prepared data for Power BI and machine learning integrations.

🔹 Project Impact
This project demonstrates how powerful SQL alone can be for building complete ETL pipelines. By working through every layer of data transformation manually, it highlights real-world data engineering skills:
From raw ingestion to refined insights — every layer adds business value and trust in data.

📸 Visual References
Medallion Architecture (Bronze → Silver → Gold)
SQL Data Warehouse Flow
Star Schema Diagram (Fact & Dimension Tables)

💡 Future Enhancements
Automate ETL with SSIS / Azure Data Factory
Integrate with Power BI dashboard for sales insights
Add data quality scorecards and error tracking

👩‍💻 Author
Sneha Busi
Data Analyst | SQL | Power BI | Data Modeling | Machine Learning

📬 Connect with me on LinkedIn 
https://www.linkedin.com/in/sneha1631/



