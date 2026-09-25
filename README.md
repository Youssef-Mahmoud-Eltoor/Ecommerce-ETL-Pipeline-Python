# 🛒 E-Commerce Orders ETL & Temporal Analysis Pipeline

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=for-the-badge&logo=sqlite)
![ETL](https://img.shields.io/badge/Pipeline-ETL-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

An end-to-end data engineering pipeline designed to ingest, clean, validate, transform, analyze, and persist large-scale e-commerce order records. The pipeline enforces strict data quality policies, derives temporal and geographic features, answers core business questions, and records full operational audit logs.

---

## 👥 Team Members & Credits
* **Youssef Mahmoud ElToor** - *Data Engineer*
* **Karim Hany Nasr** - *Data Engineer*

**Course:** Big Data Engineering with Python  
**Project:** E-Commerce Orders ETL & Geographic/Temporal Analysis  

---

## ⚙️ Operational Architecture & Pipeline Flow

The following flow diagram illustrates the robust, modular architecture (`Extract → Transform → Analyze → Load → Log`) implemented to process e-commerce orders:

```text
[ Raw Order Datasets ] 
       │   (data/raw/orders.csv)
       ▼
┌────────────────────────────────────────────────────────┐
│ 1. EXTRACT STAGE                                       │
│    ├── File Validation & Ingestion (pandas)            │
│    └── Exception Handling & Input Shape Logging        │
└────────────────────────────────────────────────────────┘
       │
       ▼
┌────────────────────────────────────────────────────────┐
│ 2. TRANSFORM STAGE (Data Quality & Cleaning)           │
│    ├── Text Standardizing: Customer, State, City       │
│    ├── Deduplication: Order ID & Duplicate Row Removal │
│    ├── Datetime Conversion: ISO Parsing & Error handling│
│    ├── Feature Engineering: Year, Month, Weekday, Qtr  │
│    └── Geographic Composite: order_location Creation   │
└────────────────────────────────────────────────────────┘
       │
       ▼
┌────────────────────────────────────────────────────────┐
│ 3. ANALYZE STAGE (Descriptive Business Intelligence)   │
│    ├── Geographic Breakdown: Orders by State & City    │
│    ├── Temporal Trends: Peak Months, Days, Quarters    │
│    └── Data Quality Audit Metrics                      │
└────────────────────────────────────────────────────────┘
       │
       ▼
┌────────────────────────────────────────────────────────┐
│ 4. LOAD STAGE (Persistence & Storage)                  │
│    ├── Output Clean CSV: data/output/cleaned_orders.csv│
│    ├── Aggregated Summaries: data/output/summary_*.csv │
│    └── Relational Storage: data/output/orders.db       │
└────────────────────────────────────────────────────────┘
       │
       ▼
[ Execution Monitoring Log: logfile.txt ]
