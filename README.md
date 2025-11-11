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

🔸 Gold Layer – Business
Contains business-ready data models using a Star Schema.
Combines cleaned datasets to create fact and dimension tables:
gold.fact_sales
gold.dim_customers
gold.dim_products

Implements business logic such as:
Sales_Amount = Quantity * Price
Enables BI tools like Power BI / Tableau for visualization.

📊 Data Model (Star Schema)

Fact Table:
gold.fact_sales → Stores metrics such as quantity, price, sales amount, and foreign keys linking to dimensions.

Dimension Tables:
gold.dim_customers → Customer details (demographics, marital status, country, etc.)
gold.dim_products → Product details (category, maintenance status, cost, etc.)

Relationships:
fact_sales.customer_key → dim_customers.customer_key
fact_sales.product_key → dim_products.product_key

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



