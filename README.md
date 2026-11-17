# ETL Pipeline with Databricks

## Overview

Rio Mart is a quick-commerce business that delivers groceries to customers within 10 minutes. This ten-minute promise is more than a marketing strategy — it is the foundation of its business model.

To maintain this promise, Rio Mart needs to monitor delivery performance, identify operational bottlenecks, evaluate rider performance, and understand product profitability.

However, raw data alone cannot provide these insights. It needs to be transformed into clean, structured, and analytics-ready data.

This project focuses on building an ETL pipeline using **Databricks** to transform raw data into meaningful business insights.

It addresses three key business questions:

1. **Delivery Performance:** Which city is failing to meet the 10-minute delivery promise?
2. **Rider Performance:** Who are the top-performing riders, and who needs improvement?
3. **Product Profitability:** Which products generate the highest profit?


## Project Objectives

- Build an end-to-end ETL pipeline using Databricks
- Process raw data and transform it into structured datasets
- Implement Medallion Architecture
- Apply data cleaning, transformation, and aggregation using PySpark
- Create analytics ready datasets to support business decision-making


## Architecture

This project follows the Medallion Architecture (Multi-Hop Architecture) in Databricks, organizing data processing into three layers: Bronze, Silver, and Gold.

**🥉[Bronze Layer](https://github.com/tyagi-mansi11/ETL-Pipeline-with-Databricks/blob/2d0e8e42389fd54960ae3e6a251feb87242657c7/rio_mart/01_bronze_layer.ipynb)**
- Reads raw source files from Unity Catalog Volumes
- Ingests data into Bronze tables
- Preserves the raw data for downstream processing

**🥈[Silver Layer](https://github.com/tyagi-mansi11/ETL-Pipeline-with-Databricks/blob/2d0e8e42389fd54960ae3e6a251feb87242657c7/rio_mart/02_silver_layer.ipynb)**
- Reads data from Bronze tables
- Performs data cleaning and transformation
- Handles data quality and consistency

**🥇[Gold Layer](https://github.com/tyagi-mansi11/ETL-Pipeline-with-Databricks/blob/2d0e8e42389fd54960ae3e6a251feb87242657c7/rio_mart/03_gold_layer.ipynb)**
- Reads processed data from Silver tables
- Applies business-level transformations and aggregations
- Creates analytics-ready tables for business reporting and analysis


## Project Organization

The project uses Databricks Unity Catalog and Workspace to organize its data and processing logic.

- **Raw Data:** Source files are stored in a Unity Catalog Volume
- **Bronze, Silver, and Gold:** Processed Delta tables are maintained in Unity Catalog
- **Notebooks:** ETL logic for ingestion, transformation, and data processing is maintained in the Databricks Workspace


```text
Databricks
│
├── Workspace
│   └── Users
│       └── <user-email-id>
│           └── rio_mart/
│               ├── Bronze Notebook
│               ├── Silver Notebook
│               └── Gold Notebook
│
├── Unity Catalog
│   └── workspace
│       └── rio_mart_quick_commerce
│           │
│           ├── Volume
│           │   └── raw/
│           │       └── Raw Source Files
│           │
│           └── Tables
│               ├── Bronze Tables
│               ├── Silver Tables
│               └── Gold Tables
```

### Data Processing Flow

1. Raw source files are stored in the Unity Catalog Volume.
2. Bronze notebook reads raw files and creates Bronze tables.
3. Silver notebook processes Bronze tables and creates cleaned Silver tables.
4. Gold notebook transforms Silver tables into business-ready Gold tables for analysis and reporting.


## Technology Stack

- **Databricks** – Data engineering and processing platform
- **Unity Catalog** – Data governance and organization
- **Delta Lake** – Data storage and management


## Business Use Cases

| Business Question | Expected Outcome |
|---|---|
| Which city is missing the 10-minute delivery target? | Identify cities with delivery delays and operational bottlenecks. |
| Who are the best-performing riders? | Evaluate rider performance and identify improvement areas. |
| Which products are making money? | Understand product-level profitability and support better business decisions. |

