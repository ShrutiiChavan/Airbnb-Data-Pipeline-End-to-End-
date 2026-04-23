# 🏠 Airbnb End-to-End Data Engineering Project

## 📋 Overview

This project showcases a scalable end-to-end data engineering pipeline for Airbnb data built on modern cloud platforms. Using Snowflake, dbt, and AWS, it demonstrates robust data warehousing and transformation practices.

Data from listings, bookings, and hosts is processed through a medallion architecture (Bronze → Silver → Gold), with support for incremental loading and Slowly Changing Dimensions (SCD Type 2), resulting in high-quality, analytics-ready data models.


### Data Flow
```
Source Data (CSV) → AWS S3 → Snowflake (Staging) → Bronze Layer → Silver Layer → Gold Layer
                                                           ↓              ↓           ↓
                                                      Raw Tables    Cleaned Data   Analytics
```

### Technology Stack

- **Cloud Data Warehouse**: Snowflake
- **Transformation Layer**: dbt (Data Build Tool)
- **Cloud Storage**: AWS S3 (implied)
- **Version Control**: Git
- **Python**: 3.12+
- **Key dbt Features**:
  - Incremental models
  - Snapshots (SCD Type 2)
  - Custom macros
  - Jinja templating
  - Testing and documentation


### Medallion Architecture

Bronze Layer

Raw, unprocessed data ingested from source systems:

bronze_bookings, bronze_hosts, bronze_listings
Silver Layer

Cleaned and enriched data with standardized formats and validations:

silver_bookings, silver_hosts, silver_listings
Gold Layer

Analytics-ready datasets for reporting and modeling:

obt – Denormalized master table
fact – Fact table for analysis


## 📂 Dataset
- Airbnb listings dataset  
- Includes:
  - Price  
  - Location  
  - Availability  
  - Host details  

## 📌 How to Run

1. Upload dataset to AWS S3  
2. Create external/internal stages in Snowflake  
3. Load data into Snowflake tables  
4. Run dbt models for transformation  
5. Query final datasets from Gold layer  

## 📌 Conclusion
This project showcases practical implementation of modern Data Engineering concepts including ETL pipelines, data modeling, and performance optimization using cloud-based tools.

---

⭐ If you found this project useful, feel free to star this repository!


