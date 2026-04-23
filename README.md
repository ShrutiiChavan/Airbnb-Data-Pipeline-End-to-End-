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
Ephemeral models for transformation logic
Snapshots (SCD Type 2)

Maintains historical data changes:

dim_bookings, dim_hosts, dim_listings
