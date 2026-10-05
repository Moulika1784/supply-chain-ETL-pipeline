# 🚚 Supply Chain ETL Pipeline

A data engineering project that implements an **ETL (Extract, Transform, Load) pipeline** for processing supply chain data. The pipeline extracts raw data from source files, cleans and transforms it, performs data quality checks, and loads the processed data into a structured destination for analysis and reporting.

---

## 📌 Project Overview

Supply chain operations generate data across multiple stages, including:

* 📦 Orders
* 🚛 Shipments
* 🏭 Suppliers
* 🏢 Warehouses
* 📍 Inventory
* 💰 Sales
* ⏱️ Delivery information

This project demonstrates how raw supply chain data can be transformed into a clean, structured, and analysis-ready dataset using an automated ETL workflow.

### ETL Workflow

```text
        ┌─────────────────────┐
        │    Source Data      │
        │ CSV / Excel / DB    │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │      EXTRACT        │
        │ Read & Collect Data │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │     TRANSFORM       │
        │                     │
        │ • Clean Data        │
        │ • Handle Missing    │
        │ • Remove Duplicates │
        │ • Standardize Data  │
        │ • Validate Records  │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │        LOAD         │
        │ Structured Database │
        │ / Data Warehouse    │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │ Analysis & Reporting│
        └─────────────────────┘
```

---

## 🎯 Objectives

The main objectives of this project are to:

* Build a complete **ETL pipeline**
* Process raw supply chain data efficiently
* Improve data quality and consistency
* Handle missing and duplicate records
* Standardize data formats
* Perform data validation
* Store transformed data in a structured format
* Create analysis-ready datasets
* Demonstrate practical **data engineering concepts**

---

## 🛠️ Tech Stack

| Technology                    | Purpose                              |
| ----------------------------- | ------------------------------------ |
| **Python**                    | ETL pipeline development             |
| **Pandas**                    | Data manipulation and transformation |
| **SQL**                       | Data querying and storage            |
| **Git & GitHub**              | Version control                      |
| **CSV / Excel**               | Source data                          |
| **Database / Data Warehouse** | Processed data storage               |

> The exact storage and orchestration technologies can be updated based on the implementation.

---

## 📂 Project Structure

```text
Supply-Chain-ETL-Pipeline/
│
├── data/
│   ├── raw/
│   │   └── supply_chain_data.csv
│   │
│   └── processed/
│       └── cleaned_supply_chain_data.csv
│
├── src/
│   ├── extract.py
│   ├── transform.py
│   ├── load.py
│   └── pipeline.py
│
├── sql/
│   ├── create_tables.sql
│   └── analysis_queries.sql
│
├── notebooks/
│   └── data_exploration.ipynb
│
├── tests/
│   └── test_pipeline.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 🔄 ETL Pipeline

### 1. Extract

The extraction stage collects raw supply chain data from the configured source.

Example sources include:

```text
CSV
Excel
Database
API
```

The extracted data is loaded into the processing environment for transformation.

---

### 2. Transform

The transformation stage prepares the raw data for downstream analysis.

Typical transformations include:

* Handling missing values
* Removing duplicate records
* Standardizing column names
* Converting data types
* Formatting dates
* Cleaning text fields
* Validating numerical values
* Standardizing categorical values
* Creating derived columns
* Filtering invalid records

Example:

```text
Raw Data
   ↓
Remove Duplicates
   ↓
Handle Missing Values
   ↓
Standardize Formats
   ↓
Validate Records
   ↓
Create Derived Fields
   ↓
Clean Dataset
```

---

### 3. Load

The transformed dataset is loaded into the target storage system.

The destination can be:

* Relational database
* Data warehouse
* Processed CSV files
* Cloud storage

The loaded data is structured so that it can be consumed by downstream analytics and reporting applications.

---

## 🧹 Data Quality Checks

The pipeline performs data-quality checks such as:

* ✅ Missing-value validation
* ✅ Duplicate detection
* ✅ Data-type validation
* ✅ Date-format validation
* ✅ Numerical-value validation
* ✅ Required-field validation
* ✅ Invalid-record detection

Example validation:

```python
assert df["order_id"].notna().all()
assert df["quantity"].ge(0).all()
assert df["order_date"].notna().all()
```

---

## 📊 Supply Chain Data

The pipeline can work with fields such as:

| Field             | Description             |
| ----------------- | ----------------------- |
| `order_id`        | Unique order identifier |
| `product_id`      | Product identifier      |
| `supplier_id`     | Supplier identifier     |
| `warehouse_id`    | Warehouse identifier    |
| `order_date`      | Date of order           |
| `quantity`        | Quantity ordered        |
| `unit_price`      | Price per unit          |
| `shipping_date`   | Shipment date           |
| `delivery_date`   | Delivery date           |
| `inventory_level` | Available inventory     |
| `delivery_status` | Delivery status         |

The actual columns can be modified according to the source dataset.

---

## ▶️ How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd Supply-Chain-ETL-Pipeline
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on Linux/macOS:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Add Source Data

Place the raw supply chain dataset inside:

```text
data/raw/
```

### 5. Run the Pipeline

```bash
python src/pipeline.py
```

The pipeline will:

```text
Extract → Transform → Validate → Load
```

---

## 📈 Data Analysis

After the ETL process is completed, the cleaned dataset can be used to analyze:

* Order volume
* Inventory levels
* Supplier performance
* Delivery performance
* Shipping delays
* Product demand
* Warehouse operations
* Sales trends
* Supply chain efficiency

Example SQL:

```sql
SELECT
    supplier_id,
    COUNT(order_id) AS total_orders,
    AVG(quantity) AS avg_quantity
FROM supply_chain
GROUP BY supplier_id
ORDER BY total_orders DESC;
```

---

## ⚡ Key Features

* 🔄 End-to-end ETL workflow
* 🧹 Automated data cleaning
* 🔍 Data validation
* 📊 Structured supply chain dataset
* 🗄️ Database-ready output
* 📈 Analysis-ready data
* 🐍 Python-based processing
* 🛠️ Modular ETL architecture
* 📋 SQL-based analysis

---

## 🔮 Future Enhancements

* [ ] Add Apache Airflow orchestration
* [ ] Add cloud storage integration
* [ ] Add AWS S3 support
* [ ] Add automated database loading
* [ ] Add real-time data ingestion
* [ ] Add pipeline monitoring
* [ ] Add logging and error handling
* [ ] Add automated data-quality reports
* [ ] Add Power BI dashboard
* [ ] Add CI/CD pipeline
* [ ] Add scheduled ETL execution

---

## 📚 Key Concepts Demonstrated

This project demonstrates practical knowledge of:

**ETL Pipelines • Data Engineering • Data Cleaning • Data Transformation • Data Validation • SQL • Python • Data Warehousing • Supply Chain Analytics • Data Quality**

---

## 👩‍💻 Author

**Moulika Mallula**

Computer Science & Engineering — Artificial Intelligence & Machine Learning

---

## ⭐ Project Summary

> **A practical end-to-end ETL pipeline that transforms raw supply chain data into clean, validated, structured, and analysis-ready data.**

```text
Raw Supply Chain Data
        ↓
     Extract
        ↓
    Transform
        ↓
 Data Quality Checks
        ↓
       Load
        ↓
Clean Analytics-Ready Data
```

---
