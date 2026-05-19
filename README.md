# ETL-with-Python-Generator
ETL pipeline built on Databricks - Customer data generation and ingestion, transformation and Load on Delta


🚀 Databricks ETL Pipeline — Customer Data

A beginner-friendly, end-to-end ETL (Extract, Transform, Load) pipeline built on Databricks Free Edition using Python and Apache Spark. This project is designed as a learning resource for anyone getting started with data engineering on Databricks.


📌 Project Overview

This pipeline simulates a real-world data engineering workflow:
Phase                             Description
Extract                Generate synthetic customer data using Python (Faker)
Transform              Clean, type-cast, and enrich the data using PySpark
Load                   Write the final dataset as a Delta table in Unity Catalog


🏗️ Architecture

[Python + Faker]          [PySpark Transformations]       [Databricks Unity Catalog]
  Generate 1000             Clean + Enrich Data            Delta Table (customers)
 Customer Records    →      Add Derived Columns      →     main.my_schema.customers


📂 Project Structure

databricks-etl-pipeline/
│
├── notebooks/
│   └── phase1_customer_etl.ipynb   # Main ETL notebook (Databricks)
│
└── README.md                        # You are here


🛠️ Tech Stack

Platform: Databricks Free Edition
Language: Python 3
Libraries: PySpark, Faker, UUID
Storage Format: Delta Lake
Catalog: Unity Catalog (Databricks)


📋 Prerequisites

Before running this pipeline, make sure you have:
A free Databricks account
A catalog and schema created in Unity Catalog
A running cluster attached to your notebook


▶️ How to Run

Clone or download this repo
Import the .ipynb notebook into your Databricks workspace:
Go to your Databricks workspace
Click "Import" and upload the .ipynb file
Update the configuration in Cell 2:
    CATALOG_NAME = "main"         # Your catalog name
    SCHEMA_NAME  = "my_schema"    # Your schema name
Attach a cluster and run all cells top to bottom


🔍 What the Pipeline Does

**Extract**
Generates 1000 synthetic customer records with fields like:
customer_id, first_name, last_name, email, phone
city, country, age, gender
signup_date, last_login_date, is_active
customer_tier (Bronze / Silver / Gold / Platinum)
total_spent_usd

**Transform**
Applies the following transformations using PySpark:
Casts date strings to DateType
Normalizes emails to lowercase
Derives full_name from first and last name
Calculates days_since_signup
Segments customers by spend into Low / Medium / High / VIP
Adds ingested_at pipeline timestamp
Drops records with null customer_id or email

**Load**
Writes the final DataFrame as a managed Delta table in Unity Catalog:
main.my_schema.customers


🗺️ Roadmap

 Phase 1 — Data Generation & Ingestion (current)
 Phase 2 — Gold Layer (aggregated summary tables)
 Phase 3 — Data Quality Checks
 Phase 4 — Scheduled Databricks Jobs


🙌 Acknowledgements

Faker — for synthetic data generation
Apache Spark — for distributed data processing
Databricks — for the unified data platform


📄 License

This project is open source and available under the MIT License.
