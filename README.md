# 📊 Marketing Project: Olist E-commerce Analytics

## Project Overview
This project implements a complete Data Engineering pipeline using the **Databricks Unity Catalog** and **Medallion Architecture**. The goal is to transform raw e-commerce data into an actionable **RFM (Recency, Frequency, Monetary)** Customer Segmentation model for marketing decision-making.



## Architecture & Governance
The project is modularized into four main notebooks, ensuring high governance, scalability, and data discovery through deep documentation (comments) directly in the Catalog.

* **Bronze Layer:** Raw ingestion from Kaggle API into secure Unity Catalog Volumes.
* **Silver Layer:** Data refinement, deduplication of geographical records, and consolidation of transactional payments.
* **Gold Layer:** Business-level aggregations, statistical quintile scoring, and final RFM customer labeling.

## Tech Stack
* **Language:** PySpark (Python) & Spark SQL
* **Platform:** Databricks (Premium Tier / Unity Catalog)
* **Storage:** Delta Lake (Parquet-based)
* **Ingestion:** Kaggle API & Databricks Volumes
* **Visualization:** Power BI (via SQL Warehouse)

## 📈 Business Intelligence & Insights
The final layer of this pipeline connects directly to **Power BI** via **Databricks SQL Warehouse**, providing a real-time executive view of the customer base.

### Key Visualizations:
* **Customer Segmentation Map:** A distribution of the 5 RFM segments to identify where the revenue is concentrated.
* **Geospatial Sales Heatmap:** Analysis of sales density across Brazilian states using Latitude/Longitude data from the Gold layer.
* **Revenue vs. Recency:** Identifying the "Sweet Spot" of customers who buy frequently and have high monetary value.
* **At-Risk Monitoring:** A proactive list of high-value customers who haven't purchased in a significant period.

### Connection Method:
* **Connector:** Azure Databricks (DirectQuery for real-time updates).
* **Authentication:** Personal Access Token (PAT).
* **Performance:** Leverages Delta Lake's indexing for fast cross-filtering of millions of records.

## Key Engineering Features
* **Idempotent Pipelines:** All notebooks are designed to be re-run without data duplication (`overwrite` mode).
* **Data Governance:** Full documentation of Schemas, Tables, and Columns within the Unity Catalog for easy Data Discovery.
* **Security:** Use of secure Volumes for raw file handling, preventing unauthorized local file system access.
* **Business Intelligence:** Advanced segmentation logic (Champions, At Risk, Loyal Customers) calculated at the engine level to optimize Power BI performance.

## How to Navigate
1.  `01_Infrastructure_Setup`: Schema and Volume creation.
2.  `02_Bronze_Ingestion`: Cloud-to-Cloud data extraction.
3.  `03_Silver_Refinement`: Quality filters and relational joins.
4.  `04_Gold_Analytics`: RFM Scoring and Marketing labels.
