# Bike Data Lakehouse

A data engineering project built on **Databricks Community Edition** that processes bike sales data using the **Medallion Architecture** (Bronze → Silver → Gold).

---

## What This Project Does

Raw bike sales data from CRM and ERP source systems is ingested and progressively cleaned and transformed across three layers until it is ready for business reporting and analysis.

---

## Architecture

```
Raw Data  →  Bronze  →  Silver  →  Gold
```

- **Bronze** — Raw data ingested as-is from source systems (CRM & ERP)
- **Silver** — Data cleaned, nulls removed, formats standardized per source
- **Gold** — Final business-ready tables for reporting and analysis

---

## Tools & Technologies

- **Databricks Community Edition** — Notebook environment & cluster
- **Apache Spark / PySpark** — Data processing and transformations
- **Delta Lake** — Reliable data storage with ACID transactions
- **Python & SQL** — Transformations and queries

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

## How to Run

1. Upload notebooks to **Databricks Community Edition**
2. Attach to a running cluster
3. Run notebooks in this order:
   - `Bronze.ipynb` → All Silver notebooks → All Gold notebooks

---

## Author

**Vinay Sharma**  
GitHub: [vinaysharma-HP](https://github.com/vinaysharma-HP)
