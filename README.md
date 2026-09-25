# 🛒 E-Commerce End-to-End Data Pipeline

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![ETL](https://img.shields.io/badge/Pipeline-ETL-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 👥 Team Members
* **Youssef Mahmoud ElToor** - *Data Engineer*
* **Kareem Hany Nasser** - *Data Engineer*

---

## 📝 Project Overview
This project delivers an automated **End-to-End Data Pipeline (ETL)** built with **Python** and **Pandas** to extract, clean, transform, and log sales and transaction data from an E-Commerce platform. 

The pipeline ensures data integrity, handles missing values, generates analytical metrics, and logs execution details into an automated system monitoring file (`logfile.txt`).

---

## ⚙️ Key Technical Features
* **Data Extraction:** Automated ingestion of multi-source raw CSV datasets.
* **Data Cleaning & Preprocessing:** Handling null values, data type casting, and duplicate removal.
* **Feature Engineering:** Calculating key performance indicators (KPIs) such as customer lifetime sales, total revenue, and transactional metrics.
* **Pipeline Logging System:** Custom logging execution script to track operational status and errors in real-time.

---

## 📁 Repository Structure
```text
├── Dataset/                   # Raw E-commerce source files
├── output/                    # Transformed output datasets
├── E - commerce Project Pipeline.ipynb   # Main Jupyter Notebook Pipeline
├── logfile.txt                # Automated execution log
└── README.md                  # Project documentation
