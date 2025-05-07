# Retail Data Analytics Project

## Overview
This project implements a complete retail analytics solution, transforming raw sales data into actionable business insights. The system incorporates data engineering, data warehousing, data quality, and data visualization components to provide a comprehensive view of retail operations.

## Project Architecture
The project follows a modern data stack architecture:
- **Data Extraction & Loading**: Python scripts to extract data from source systems and load into the data warehouse
- **Data Transformation**: dbt for transforming raw data into analytics-ready models
- **Data Warehouse**: Google BigQuery for storing and processing data
- **Data Quality**: Soda for data quality checks and monitoring
- **Orchestration**: Airflow via Cosmos CLI for workflow management
- **Data Visualization**: Google Looker Studio for creating interactive dashboards and reports
- **Infrastructure**: Docker for containerization and deployment

## Implemented Components

### Data Pipeline
- Setup data extraction from source systems
- Implemented ELT processes to move data to BigQuery
- Created scheduled data refresh jobs using Airflow

### Data Warehouse (BigQuery)
- Established a structured data warehouse with appropriate schemas
- Configured user access controls and security measures
- Set up computational resources and optimization

### Data Transformation (dbt)
- Implemented dbt models for data transformation
- Created staging models for initial data cleaning
- Developed intermediate and mart models for business-specific analytics
- Integrated dbt with Airflow using Cosmos CLI

### Data Quality (Soda)
- Implemented data quality checks and monitoring
- Created tests to ensure data quality and integrity
- Set up automated alerting for data quality issues

### Orchestration (Airflow)
- Used Airflow for workflow management and scheduling
- Interfaced with Airflow via the Cosmos CLI
- Created DAGs for ELT processes, transformations, and quality checks

### Data Visualization (Looker Studio)
- Designed interactive dashboards showing key performance indicators
- Created visualizations for sales trends, product performance, and customer insights
- Implemented filters for dynamic data exploration
- Set up scheduled report generation and distribution

## Key Features
- **Sales Analysis**: Track sales performance across different dimensions (time, product, location)
- **Customer Insights**: Analyze customer behavior and purchasing patterns
- **Product Performance**: Evaluate product performance and profitability
- **Data Quality Monitoring**: Automated checks to ensure data reliability
- **Containerized Deployment**: Docker-based deployment for consistency and portability

## Technologies Used
- **Languages**: Python, SQL
- **Data Transformation**: dbt
- **Data Warehouse**: Google BigQuery
- **Data Quality**: Soda
- **Orchestration**: Airflow with Cosmos CLI
- **Data Visualization**: Google Looker Studio
- **Containerization**: Docker
- **Version Control**: Git/GitHub

## Project Structure
```
```
Pipeline-BigQuery-Airflow-dbt-Soda
├─ .dockerignore
├─ dags
│  ├─ .airflowignore
│  └─ retail.py
├─ Dockerfile
├─ include
│  ├─ dataset
│  │  └─ online_retail.csv
│  ├─ dbt
│  │  ├─ .user.yml
│  │  ├─ cosmos_config.py
│  │  ├─ dbt_packages
│  │  ├─ dbt_project.yml
│  │  ├─ logs
│  │  ├─ models
│  │  │  ├─ report
│  │  │  │  ├─ report_customer_invoices.sql
│  │  │  │  ├─ report_product_invoices.sql
│  │  │  │  └─ report_year_invoices.sql
│  │  │  ├─ sources
│  │  │  │  └─ sources.yml
│  │  │  └─ transform
│  │  │     ├─ dim_customer.sql
│  │  │     ├─ dim_datetime.sql
│  │  │     ├─ dim_product.sql
│  │  │     └─ fct_invoices.sql
│  │  ├─ packages.yml
│  │  ├─ profiles.yml
│  │  └─ target
│  │     ├─ compiled
│  │     │  └─ retail
│  │     │     └─ models
│  │     │        └─ transform
│  │     │           ├─ dim_customer.sql
│  │     │           ├─ dim_datetime.sql
│  │     │           ├─ dim_product.sql
│  │     │           └─ fct_invoices.sql
│  │     ├─ graph.gpickle
│  │     ├─ manifest.json
│  │     ├─ partial_parse.msgpack
│  │     ├─ run
│  │     │  └─ retail
│  │     │     └─ models
│  │     │        └─ transform
│  │     │           ├─ dim_customer.sql
│  │     │           ├─ dim_datetime.sql
│  │     │           ├─ dim_product.sql
│  │     │           └─ fct_invoices.sql
│  │     └─ run_results.json
│  ├─ gcp
│  └─ soda
│     ├─ checks
│     │  ├─ report
│     │  │  ├─ report_customer_invoices.yml
│     │  │  ├─ report_product_invoices.yml
│     │  │  └─ report_year_invoices.yml
│     │  ├─ sources
│     │  │  └─ raw_invoices.yml
│     │  └─ transform
│     │     ├─ dim_customer.yml
│     │     ├─ dim_datetime.yml
│     │     ├─ dim_product.yml
│     │     └─ fct_invoices.yml
│     └─ check_function.py
├─ LICENSE
├─ packages.txt
├─ plugins
├─ README.md
├─ requirements.txt
└─ tests
```

**Security Note:** All configuration files containing sensitive information and secrets have been withheld from this repository for security reasons. Users will need to create their own configuration files with appropriate credentials.

## Acknowledgements
This project was completed following the tutorial guidelines from the [Retail Project](https://robust-dinosaur-2ef.notion.site/PUBLIC-Retail-Project-af398809b643495e851042fa293ffe5b) created by the original author. The implementation follows the architecture and approaches outlined in the tutorial, with modifications.
