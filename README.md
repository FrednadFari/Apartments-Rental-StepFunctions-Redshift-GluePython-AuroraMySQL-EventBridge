# AWS Rental Apartments ETL Pipeline  
### End-to-End Data Engineering Project using AWS Glue, Amazon Redshift, AWS Step Functions & EventBridge

![Architecture Diagram](architecture.png)

---

# Project Overview

This project demonstrates a complete **cloud-based ETL / Data Processing pipeline** for Rental Apartment data using AWS services.

The pipeline extracts data from a **MySQL source system**, stores raw files in **Amazon S3**, loads data into **Amazon Redshift**, transforms data into analytics-ready layers, and automates the entire workflow using **AWS Step Functions** and **Amazon EventBridge**.

This project simulates a real-world production data engineering solution used in enterprise environments.

---

# Business Use Case

A rental apartment company needs daily updated reporting for:

- Apartment availability
- Rental prices by city
- Occupancy rates
- Revenue trends
- Apartment attributes analytics
- Executive dashboards

The raw data exists inside MySQL operational systems and must be transformed into business-ready analytics tables.

---

# Architecture Components

## Source System
- MySQL Database
- Rental apartment operational data

## Storage Layer
- Amazon S3 Raw Storage
- CSV / Parquet extracted files

## Processing Layer
- AWS Glue Jobs
- Python ETL scripts

## Data Warehouse
- Amazon Redshift

## Orchestration
- AWS Step Functions

## Scheduling
- Amazon EventBridge

---

# Full Pipeline Flow

```text
Amazon EventBridge (Daily Schedule Trigger)
        ↓
AWS Step Functions
        ↓
1. MySQL Extraction Jobs
        ↓
2. Raw Files stored in Amazon S3
        ↓
3. Redshift Raw Ingestion Jobs
        ↓
4. Data Transformation Jobs
        ↓
5. Curated Data Models
        ↓
6. Reporting / Metrics Layer
        ↓
7. BI Dashboard Consumption