# Retail Sales Data Pipeline | Azure Data Engineering Project

## Project Overview
This project demonstrates an end-to-end Azure Data Engineering solution for a retail sales business. The goal is to ingest data from multiple sources, process it through a Medallion Architecture, apply data quality rules, and make the final data available for reporting and analytics.

The pipeline uses Azure Data Factory for orchestration, ADLS Gen2 for data lake storage, Databricks/PySpark for transformations, Azure SQL Database for serving curated data, Azure Key Vault for secure credential management, and Power BI for business reporting.

## Business Problem
A retail company receives sales, customers, products, and store data from different systems such as REST APIs, SQL databases, and CSV files. The existing process is manual, time-consuming, and prone to data quality issues.

The business needs an automated cloud-based pipeline that can:
- ingest data from multiple sources
- store raw data securely
- clean and validate records
- create business-ready tables
- support reporting in Power BI
- improve data reliability and refresh efficiency

## Solution
Designed and implemented a modern Azure Data Engineering pipeline following Medallion Architecture:

- Bronze Layer: raw data ingestion
- Silver Layer: cleaned and validated data
- Gold Layer: analytics-ready business tables
- Serving Layer: Azure SQL Database and Power BI

## Architecture Flow
REST API / SQL / CSV
        ↓
Azure Data Factory Pipelines
        ↓
Bronze Layer (Raw CSV Files)
        ↓
ADF Data Flow Transformations
        ↓
Silver Layer (Cleaned Parquet Files)
        ↓
Gold Business Aggregations
        ↓
Azure SQL Reporting Tables
        ↓
Power BI Reporting

**Technologies Used**
Azure Data Factory (ADF)
Azure Data Lake Storage Gen2 (ADLS Gen2)
Azure SQL Database
Azure Key Vault
Power BI
REST API
SQL
GitHub
Draw.io

**Source Systems**
REST API
- JSONPlaceholder Users API
- JSONPlaceholder Posts API
SQL Tables
- customers
- products
- product_category
- orders
- sales
CSV File
- inventory_updates.csv

**Medallion Architecture**
**Bronze Layer**
- Stores raw ingested data from REST API, SQL tables, and CSV files without applying transformations.
**Silver Layer**
- Contains cleaned, validated, and standardized datasets transformed using ADF Mapping Data Flows and stored in Parquet format.
**Gold Layer**
- Contains business-ready aggregated datasets for reporting and analytics.
Gold datasets created:
- sales_summary_gold
- category_sales_summary_gold
- top_products_gold

**Key Transformations**
- Null and primary key validation
- Duplicate handling
- Data type conversion
- Column filtering
- CSV to Parquet conversion
- Joins and aggregations
- Gold KPI creation

**Azure SQL Reporting Layer**
Gold datasets were loaded into Azure SQL Database reporting tables using ADF Copy Activities for downstream reporting and analytics.

**Power BI Reporting**
Power BI was connected to Azure SQL Database to create dashboards for:
- Sales trends
- Category performance
- Top-selling products
- KPI reporting
  
**Validation Performed**
- Row count validation
- SQL query validation
- Pipeline validation
- Monitor execution checks
- ADLS output verification
  
**Challenges Resolved**
- Azure Key Vault RBAC permission issue
- ADLS PathNotFound error
- Datatype conversion issue during aggregation
- Wildcard Parquet loading issue
- SQL schema mismatch during Gold ingestion

**Key Learnings**
This project provided hands-on experience with:
- Azure Data Factory orchestration
- Medallion Architecture
- ADLS Gen2 storage design
- ADF Data Flow transformations
- Parquet optimization
- Azure SQL reporting integration
- GitHub project documentation
