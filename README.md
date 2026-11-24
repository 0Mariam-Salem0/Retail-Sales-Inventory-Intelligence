# Retail Sales & Inventory Intelligence with Agentic AI

An end-to-end Data Engineering, Business Intelligence, and Agentic AI project built using Microsoft Fabric.

This project integrates real-world retail sales data from the Olist dataset with simulated inventory data to build a unified analytics solution. It follows the Medallion Architecture (Bronze, Silver, Gold) and combines data engineering, semantic modeling, Power BI reporting, and AI-powered interaction.

## Project Overview

The main objective is to transform raw retail sales and inventory data into reliable, business-ready insights.

The solution enables users to:
- Analyze sales performance and revenue.
- Monitor product inventory across multiple warehouses.
- Identify low-stock products.
- Evaluate delivery performance and delays.
- Explore business data through an Agentic AI interface.

## Architecture

The project follows the Medallion Architecture:

### 1. Bronze Layer
- Stores raw Olist sales datasets.
- Stores simulated inventory data.
- Preserves the original source data.

### 2. Silver Layer
- Data cleaning and transformation using Dataflows Gen2.
- Data type correction and quality checks.
- Handling missing values and inconsistent records.
- Preparation of clean datasets for analytics.

### 3. Gold Layer
A business-ready dimensional model containing six tables:

**Fact Tables**
- FactSales
- FactInventory

**Dimension Tables**
- DimProducts
- DimCustomers
- DimWarehouse
- DimDate

The model follows a Star Schema design.

## Technology Stack

| Category | Technologies |
|---|---|
| Data Platform | Microsoft Fabric |
| Data Ingestion | Fabric Data Factory / Pipelines |
| Data Transformation | Dataflows Gen2, PySpark |
| Storage | Fabric Lakehouse |
| Data Modeling | Star Schema, Semantic Model |
| Analytics | DAX |
| Visualization | Power BI |
| AI Integration | Agentic AI, Fabric IQ MCP |
| Version Control | Git, GitHub |

## Data Sources

### Olist Dataset
A Brazilian e-commerce dataset containing retail transactions and related business information.

### Simulated Inventory Dataset
Custom-generated inventory records containing:
- inventory_id
- product_id
- warehouse_id
- stock_on_hand
- reorder_level
- last_updated

The inventory design supports multiple products across multiple warehouses.

## Gold Layer Data Model

| Table | Description |
|---|---|
| FactSales | Sales transactions at order-item level |
| FactInventory | Inventory records by product and warehouse |
| DimProducts | Product attributes |
| DimCustomers | Customer identifiers |
| DimWarehouse | Warehouse identifiers |
| DimDate | Calendar attributes |

The semantic model uses shared dimensions to analyze sales and inventory without creating a direct relationship between the two fact tables.

## Key Business Metrics

### Sales Analytics
- Total Sales
- Total Freight
- Total Revenue
- Total Orders
- Total Customers
- Average Delivery Days
- Delayed Orders
- Delayed Orders Percentage

### Inventory Analytics
- Total Stock
- Low Stock Records
- Low Stock Products
- Total Warehouses

## Power BI Reporting

An interactive report was developed to present sales and inventory insights, helping users explore business performance and identify operational issues.

## Agentic AI Integration

An Agentic AI solution was integrated with the project to enable natural-language interaction with business data.

The goal is to allow users to ask business questions and retrieve insights without manually writing queries.

Example questions:
- What are the total sales?
- Which products have low stock?
- Which warehouses contain specific products?
- What is the average delivery time?
- Which products generate the highest sales?

## Data Quality and Validation

The Gold Layer was validated through row-count and referential-integrity checks.

Validated row counts:

| Table | Rows |
|---|---:|
| FactSales | 112,650 |
| DimProducts | 32,951 |
| DimCustomers | 99,441 |
| FactInventory | 65,902 |
| DimWarehouse | 4 |
| DimDate | 3,733 |

All checked relationships passed validation, with zero missing product, customer, warehouse, and date references in the tested tables.

## Project Workflow

1. Collect raw sales and inventory data.
2. Load source data into the Bronze Layer.
3. Clean and transform data into the Silver Layer.
4. Build dimensional tables in the Gold Layer.
5. Validate data quality and relationships.
6. Create the semantic model and DAX measures.
7. Develop Power BI reports.
8. Integrate Agentic AI for natural-language data interaction.

## Repository Structure

```text
Retail-Sales-Inventory-Intelligence/
│
├── fabric/
│   ├── pipelines/
│   ├── dataflows/
│   ├── notebooks/
│   ├── semantic-model/
│   └── reports/
│
├── agentic-ai/
│   ├── src/
│   ├── tools/
│   └── config/
│
├── docs/
│   ├── architecture/
│   └── screenshots/
│
├── README.md
└── .gitignore
```

*The repository structure will be updated to match the actual exported project files.*

## Future Enhancements

- Add automated data quality monitoring.
- Extend AI capabilities with more business tools.
- Implement inventory forecasting.
- Add automated low-stock alerts.
- Improve orchestration and monitoring.

## Author

Developed as an end-to-end learning and portfolio project focused on Data Engineering, Business Intelligence, Microsoft Fabric, and Agentic AI.
