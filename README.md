# Azure End-to-End Data Pipeline with Databricks and Power BI

## Project Overview
This project demonstrates a complete data engineering pipeline from an on-premise SQL Server to Power BI dashboards, utilizing a mix of Azure services and Databricks notebooks to transform data through various stages (bronze, silver, gold).

### Key Components
- **SQL Server (on-premise)**: Initial data source where raw data is extracted.
- **Azure Blob Storage**: Acts as a staging area for raw data after extraction.
- **Databricks**: Handles data transformation in three stages: Bronze (raw), Silver (cleansed), and Gold (aggregated) tables.
- **Azure Synapse Analytics**: Serves as the data warehouse where final views are created for reporting.
- **Power BI**: Connects to Azure Synapse to create interactive dashboards for data visualization.

## Pipeline Workflow
1. **Data Ingestion**:
   - Data is extracted from on-premise SQL Server and ingested into Azure Blob Storage using Azure Data Factory.
   - The ingestion happens in batches to ensure scalability for large datasets.

2. **Data Transformation (Bronze → Silver → Gold)**:
   - **Bronze**: The raw data from Blob Storage is loaded into Databricks for initial processing and storage as Delta tables.
   - **Silver**: Cleaned and filtered data from the bronze stage is transformed and stored in silver tables, ensuring data quality and consistency.
   - **Gold**: Aggregated and business-specific transformations are applied to the silver data, ready for reporting and analytics.

3. **Data Warehousing with Azure Synapse Analytics**:
   - The gold tables are linked to Azure Synapse Analytics, where views are created for further analysis.
   - These views represent key business metrics and provide a seamless connection to reporting tools.

4. **Reporting and Visualization**:
   - Power BI connects to Azure Synapse Analytics to create dashboards, offering real-time insights and analytics for stakeholders.

## Architecture Diagram
![Screenshot 2024-10-02 185527](https://github.com/user-attachments/assets/ca5475a5-5566-4693-88a1-14be3f3adc35)


## Technologies Used
- **Azure Data Factory**: For orchestrating data movement from SQL Server to Azure Blob Storage.
- **Azure Blob Storage**: For staging data.
- **Databricks**: For data processing and transformation (Python/SQL-based notebooks).
- **Azure Synapse Analytics**: As a data warehouse for structured data.
- **Power BI**: For building dashboards and reports.
