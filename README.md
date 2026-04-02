# Bike Data Lakehouse

A data engineering project built on **Databricks Community Edition** that processes bike sales data using the **Medallion Architecture** (Bronze → Silver → Gold).

---

## What This Project Does

Raw bike sales data is ingested and progressively cleaned and transformed across three layers until it is ready for business reporting and analysis.

---

## Architecture

```
Raw Data  →  Bronze  →  Silver  →  Gold
```

- **Bronze** — Raw data ingested as-is, no changes
- **Silver** — Data cleaned, nulls removed, formats standardized
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
├── bronze/
│   └── Bronze.ipynb
├── silver/
│   └── Silver.ipynb
├── gold/
│   ├── Gold_customers.ipynb
│   └── Gold_fact_sales.ipynb
└── README.md
```

---

## How to Run

1. Upload notebooks to **Databricks Community Edition**
2. Attach to a running cluster
3. Run notebooks in this order:
   - Bronze → Silver → Gold

---

## Author

**Vinay Sharma**  
GitHub: [vinaysharma-HP](https://github.com/vinaysharma-HP)
