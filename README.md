Healthcare RCM Data Pipeline - Azure Data Engineering

Overview

The repository provides a complete Azure Data Engineering pipeline which focuses on Healthcare Revenue Cycle Management (RCM). The Medallion Architecture (Bronze, Silver, Gold) guides the project to process Electronic Medical Records (EMR), Claims Data, and ICD/CPT Codes which generates data-driven financial insights for healthcare management.

Technology Stack

Azure Data Factory (ADF) - Data ingestion from various sources.

Azure Data Lake Storage (ADLS Gen2) - Data storage (Landing, Bronze, Silver, Gold layers).

The data transformation and processing operations occur within Azure Databricks through its Delta Lake capabilities.

Azure SQL Database - Storing EMR data.

Azure Key Vault - Secure credentials management.

Unity Catalog - Data governance and security.

Parquet & Delta Tables - Optimized data storage.

Data Sources

EMR Data (Azure SQL DB)

Patients

Providers

Departments

Transactions

Encounters

The landing zone within ADLS Gen2 contains claims data stored as flat files.

NPI Data (National Provider Identifier - Public API)

The ICD Data (Diagnosis Code Mapping - Public API) provides access to diagnosis code mapping information.

The flat file data from the CPT source resides in the Landing Zone.

Medallion Architecture

The landing zone contains flat files together with API responses which are stored in ADLS.

Bronze Layer: Parquet format, raw data storage.

Silver Layer: Data cleaning, CDM (Common Data Model), SCD2 Implementation.

The Gold Layer contains Fact and Dimension Tables together with aggregated KPIs.

Key Features

Incremental & Full Load Pipelines

SCD2 Implementation for Historical Tracking

Fact & Dimension Modeling for Business Intelligence

Audit Logging for Data Quality & Monitoring

The system uses parallel processing alongside optimized data pipelines.

The system integrates Key Vault with automated workflows.

Pipeline Architecture

Bronze Layer: Ingesting raw data in Parquet format.

The SCD2 process takes place during Silver Layer operations which include cleaning and standardization tasks.

Gold Layer: Creating Fact & Dimension Tables for business analytics.

Audit Table: Logging ingestion and transformation activities.

Best Practices & Enhancements

The deployment of Key Vault served to provide secure credential storage.

The system includes optimized ADF pipelines which execute operations simultaneously.

The implementation of Unity Catalog enhances data governance in our system.

The data tracking process becomes more efficient through the addition of an is_active flag.

Ensured Data Quality Checks & Error Handling.

Future Enhancements

Real-time Data Processing

Machine Learning-based Predictive Analytics

Streaming Data Integration
