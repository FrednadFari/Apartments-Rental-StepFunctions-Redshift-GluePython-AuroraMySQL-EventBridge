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

Detailed Process Steps
1. Scheduled Trigger

Amazon EventBridge triggers the pipeline automatically based on schedule:

Daily at 6:00 AM
Weekly full refresh
Monthly reconciliation run
2. Extraction Layer

AWS Glue jobs connect to MySQL and extract source tables:

Jobs Used
MysqlExtractionJobApartments
MysqlExtractionJobApartmentVie
MysqlExtractionJobApartmentAtt

Output files are stored in Amazon S3.

3. Raw Storage Layer (Amazon S3)

Stores source data exactly as extracted.

Benefits
Cheap scalable storage
Historical retention
Replay capability
Source backup
4. Redshift Raw Ingestion

Glue jobs load raw files into Redshift raw tables.

Jobs Used
RedshiftRawIngestionApartments
RedshiftRawIngestionApartmentV
RedshiftRawIngestionApartmentA
5. Transformation & Data Modelling

AWS Glue + Python jobs transform raw data into analytics structures.

Layers
Raw Landing Zone

Original source structure.

Curated Zone

Cleaned and modeled data:

Fact tables
Dimension tables
Joins
Standardized columns
Reporting Layer

Business metrics tables:

Avg Rent by City
Vacancy Rate
Monthly Revenue
Apartment Counts
Trend KPIs
6. Workflow Orchestration

AWS Step Functions controls execution sequence.
Benefits
Sequential dependency control
Retry on failure
Monitoring
Logging
Operational visibility
7. Scheduling with Amazon EventBridge

Amazon EventBridge starts Step Functions automatically.
7. Scheduling with Amazon EventBridge

Amazon EventBridge starts Step Functions automatically.

Example Schedule
cron(0 6 * * ? *)

Runs daily at 6 AM.

Benefits
Fully automated runs
No manual execution
Reliable production scheduling
Technologies Used
Service	Purpose
MySQL	Source Database
AWS Glue	ETL Jobs
Python	Transform Logic
Amazon S3	Raw Storage
Amazon Redshift	Data Warehouse
AWS Step Functions	Workflow Orchestration
Amazon EventBridge	Scheduling
SQL	Data Modelling
Key Engineering Skills Demonstrated
ETL Pipeline Design
Cloud Data Engineering
AWS Architecture
Workflow Automation
Data Warehousing
Redshift Modelling
Python Scripting
Production Scheduling
Error Handling
Scalable Data Pipelines
Future Improvements
CI/CD deployment pipeline
Terraform infrastructure as code
Data quality validation checks
SNS alerts on failures
Incremental CDC loading
Dashboard integration with QuickSight
Why This Project Matters

This project reflects a real enterprise data engineering solution where operational data is transformed into trusted analytics assets using modern AWS services.

It demonstrates both technical implementation and production architecture thinking.
Fardis
