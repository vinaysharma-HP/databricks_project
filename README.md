# Bike Data Lakehouse

A data engineering project built on **Databricks Community Edition** that processes bike sales data from CRM and ERP systems using the **Medallion Architecture** (Bronze → Silver → Gold).

---

## What This Project Does

Ingests raw bike sales data from two source systems (CRM and ERP), cleans and standardizes it in the Silver layer, and builds business-ready dimension and fact tables in the Gold layer for reporting and analysis.

---

## Architecture

```
CRM & ERP Raw Data
        │
        ▼
🥉 Bronze  →  Raw data stored as-is
        │
        ▼
🥈 Silver  →  Cleaned, renamed, normalized
        │
        ▼
🥇 Gold    →  Dimension & fact tables for reporting
```

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Databricks Community Edition** | Notebook environment & Spark cluster |
| **Apache Spark / PySpark** | Distributed data transformations |
| **Delta Lake** | ACID-compliant data storage |
| **Python & SQL** | Data processing and querying |

---

## Project Structure

```
databricks_project/
│
├── bronze/
│   └── Bronze.ipynb                    # Raw ingestion from CRM & ERP sources
│
├── silver/
│   ├── Silver_crm_cust_info.ipynb      # CRM customer information
│   ├── Silver_crm_prd_info.ipynb       # CRM product information
│   ├── Silver_crm_sales_details.ipynb  # CRM sales transactions
│   ├── Silver_erp_loc_a101.ipynb       # ERP location data
│   ├── Silver_erp_cust_az12.ipynb      # ERP customer data
│   └── Silver_erp_px_cat_g1v2.ipynb    # ERP product category data
│
├── gold/
│   ├── Gold_customers.ipynb            # Customer dimension table
│   ├── Gold_fact_sales.ipynb           # Sales fact table
│   └── Gold_products.ipynb             # Product dimension table
│
└── README.md
```

---

## Layer Details

### 🥉 Bronze — Raw Ingestion
- Loads raw data from CRM and ERP source systems
- No transformations applied
- Data preserved as-is for reprocessing if needed

### 🥈 Silver — Data Cleaning & Standardization
Applied the following transformations on each source:
- **Removed nulls** — dropped or handled missing values
- **Renamed columns** — standardized column names across CRM and ERP sources
- **Trimmed whitespace** — cleaned leading/trailing spaces in string fields
- **Normalization** — standardized formats for dates, categories, and text fields

### 🥇 Gold — Business Layer
- **Gold_customers** — Unified customer dimension combining CRM and ERP data
- **Gold_products** — Product dimension with category and pricing info
- **Gold_fact_sales** — Sales fact table ready for reporting and analysis

---

## How to Run

1. Upload notebooks to **Databricks Community Edition**
2. Attach to a running cluster
3. Run in this order:
   - `Bronze.ipynb` → Silver notebooks (all 6) → Gold notebooks (all 3)

---

## Author

**Vinay Sharma**  
GitHub: [vinaysharma-HP](https://github.com/vinaysharma-HP)
