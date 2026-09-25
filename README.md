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
📊 Analytical Business Questions AnsweredThe pipeline automates data aggregation to provide actionable answers to 5 core business questions:Top Geographic Markets: Which states and cities generate the highest order volume?Monthly Seasonality: Which months experience peak order demand and volume spikes?Weekly Order Patterns: Which weekdays are the busiest for customer purchasing?Data Quality Audit: How many duplicate, missing, or invalid records were flagged and handled?Geographic Order Concentration: Which consolidated locations (City + State) hold the largest share of overall market activity?🔍 Data Quality Policy & EvidenceTo maintain auditability, no records are silently dropped. All data cleaning events are validated and recorded:Text Normalization: Stripped leading/trailing whitespaces and standardized capitalization for CustomerName, State, and City.Temporal Integrity: Coerced Order Date into standard datetime64[ns] formats; derived time components (Year, Month, Weekday, Quarter).Quality Audit Metrics:Initial Row Count vs. Cleaned Row Count tracking.Explicit duplicate detection across primary keys (Order ID).Non-destructive missing value auditing.📁 Repository StructurePlaintextproject/
├── data/
│   ├── raw/
│   │   └── orders.csv               # Original source dataset
│   └── output/
│       ├── cleaned_orders.csv       # Transformed analytical dataset
│       ├── summary_orders.csv       # Aggregated summary metrics
│       └── orders.db                # SQLite database with clean tables
├── project.ipynb / project.py       # Main pipeline script
├── logfile.txt                      # Automated execution log with timestamps
├── .gitignore                       # Git ignore configuration
└── README.md                        # Documentation
🛠️ Tech Stack & DependenciesLanguage: Python 3.9+   Data Processing: pandas, numpy   Database & Storage: sqlite3   Environment: Jupyter Notebook / VS Code   Installation & ExecutionClone the repository:Bashgit clone [https://github.com/Youssef-Mahmoud-Eltoor/Ecommerce-ETL-Pipeline-Python.git](https://github.com/Youssef-Mahmoud-Eltoor/Ecommerce-ETL-Pipeline-Python.git)
cd Ecommerce-ETL-Pipeline-Python
Install required packages:Bashpip install pandas numpy jupyter
Run the ETL Pipeline:Execute the notebook project.ipynb sequentially or run the Python pipeline script:Bashpython project.py
Verify Outputs:Check data/output/ for output CSV/SQLite files and inspect logfile.txt for execution verification.📄 LicenseThis project is open-source under the MIT License.
