# Databricks Data Engineering Project — Atliqon and SportsBar Orders Pipeline

## Overview
End-to-end pipeline ingesting raw CSV order data from AWS S3 into 
a Delta Lake medallion architecture (Bronze → Silver → Gold) using 
PySpark on Databricks.

Atliqon is parent company which sells sports equipments and has recently acquired 
Sportsbar Gmbh which sells sports nutrition items. The child company sales data is not 
in the matching format, reporting cycles are indifferent and some data is non existent.
The child company does not have a data engineering and a OLAP system. In order to unify 
supply chain, forecasting  and inventory planning, data of both the companies need to be
consistent and metrics needs to be matched. A unified data layer with consistent data 
from both companies needs to be made to drive business decisions. 


## Tech Stack
- Databricks (PySpark, Delta Lake)
- AWS S3 (external storage)
- Unity Catalog (data governance)
- GitHub (version control)


## 🏗️ Architecture
**S3 Landing → Bronze → Silver → Gold**

- **Bronze**: raw ingested data  
- **Silver**: cleaned and standardized data  
- **Gold**: aggregated, business-ready datasets  

![Architecture Diagram](data_architecture.png)


**Folder structure:**

databricks-project/
├── README.md
├── consolidate_pipeline/
│   ├── Setup
│       ├──Setupcatalogs.ipynb
│       ├──dim_data_table_creation.ipynb
│       ├──utilities.ipynb
│   ├── Dimension Data Processing
│       ├──customer_data_processing.ipynb
│       ├──2_product_data_processing.ipynb
│       ├──3_pricing_data_processing.ipynb
│   ├── 03_fact_data_processing
│       ├──01_full_load_fact.ipynb
│       ├──2_incremental_load_fact.ipynb       
└── data_architecture.png     
