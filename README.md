# Azure Data Engineering Project – End-to-End Data Pipeline

## Project Overview

This project focuses on building a data engineering pipeline using **Azure Data Factory (ADF)** to move data from different sources into Azure cloud storage, process it, and prepare it for analytical use.

The project follows a data engineering workflow covering data ingestion, pipeline orchestration, transformation, incremental loading, and data organization using the Medallion Architecture.

The objective is to understand how real-world data pipelines are designed, automated, and managed using Microsoft Azure services.

## Technologies Used

- **Azure Data Factory (ADF):** Building and orchestrating data pipelines.
- **Azure Data Lake Storage Gen2 (ADLS Gen2):** Storing ingested data.
- **Self-Hosted Integration Runtime (SHIR):** Connecting Azure Data Factory to local/on-premises files.
- **Azure SQL Database:** Relational data storage and querying.
- **PySpark:** Data transformation and processing.
- **GitHub:** Version control and project management.

## Architecture

The project follows a source-to-target data pipeline:

1. Data is collected from different sources such as local files and APIs.
2. Azure Data Factory manages and orchestrates the ingestion process.
3. Data is stored in Azure Data Lake Storage.
4. Data is transformed and organized into different layers.
5. Processed data is prepared for business reporting and analytics.

## Implementation

### 1. Azure Resource Setup

Created and configured the required Azure resources:

- Resource Group
- Azure Storage Account
- Azure Data Factory
- Azure Data Lake Storage Gen2

Configured linked services to establish connections between Azure services and data sources.

### 2. On-Premises to Azure Data Lake Migration

Built an ingestion pipeline to transfer CSV files from a local Windows folder to Azure Data Lake Storage Gen2.

**Key concepts implemented:**

- Configured a Self-Hosted Integration Runtime to allow Azure Data Factory to access local files.
- Created linked services for the local file system and Azure Data Lake.
- Created parameterized datasets to handle multiple CSV files.
- Used a ForEach activity to iterate through a list of files.
- Used a Copy Data activity to transfer files into the Bronze layer.
- Used dynamic expressions to pass file names during pipeline execution.

### 3. Dynamic Pipelines and Column Mapping

Designed the pipeline to support multiple files without creating separate Copy Data activities for each file.

**Key concepts:**

- Pipeline parameters
- Dataset parameters
- Dynamic content and expressions
- ForEach activity
- Dynamic column mapping

The goal is to make the pipeline reusable and reduce manual configuration when handling multiple datasets with different column structures.

## Project Structure

```text
Azure-Data-Engineering-Project/
│
├── README.md
│
├── adf/
│   ├── pipeline/
│   ├── dataset/
│   └── linkedService/
│
├── data/
│   └── sample-csv-files/
│
└── documentation/
    └── architecture/
```

*The folder structure represents the intended organization of the project. Update it as the actual exported ADF files and documentation are added to GitHub.*

## Azure Data Engineering Concepts Covered

The broader project learning roadmap includes:

| Area | Concepts |
|---|---|
| Data Ingestion | On-premises to Azure, API ingestion |
| Pipeline Development | ADF pipelines, activities, parameters |
| Dynamic Pipelines | ForEach, dynamic expressions, column mapping |
| Data Storage | ADLS Gen2, Azure SQL Database |
| Data Loading | Incremental loading |
| Orchestration | Pipeline dependencies and execution |
| Automation | Azure Logic Apps and triggers |
| Transformation | PySpark |
| Data Architecture | Bronze, Silver, Gold layers |
| Version Control | Azure Data Factory Git integration with GitHub |

## What I Learned

- How Azure Data Factory connects different data sources.
- How Self-Hosted Integration Runtime enables access to local data.
- How linked services and datasets work together.
- How to build reusable pipelines using parameters and dynamic expressions.
- How to use ForEach and Copy Data activities for multiple-file ingestion.
- How to organize data using the Medallion Architecture.
- How GitHub integration supports version control for Azure Data Factory.

## How to Explain This Project in an Interview

"I am building an Azure Data Engineering project where I use Azure Data Factory to create data ingestion pipelines. I started by setting up the required Azure resources and connecting my local system to Azure using a Self-Hosted Integration Runtime.

I then created linked services and parameterized datasets to move multiple CSV files from my local system into Azure Data Lake Storage Gen2. I used ForEach and Copy Data activities to make the pipeline dynamic instead of creating separate pipelines for every file.

I am also learning how to extend this workflow with API ingestion, incremental loading, PySpark transformations, and Bronze, Silver, and Gold data layers."

---

**Project Status:** In Progress

More pipeline implementations and transformations will be added as the project develops.
