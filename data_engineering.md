# Data Engineering 101

# Table of Contents
1. [Extract, Transform, Load](#etl)
2. [Data Frameworks](#frameworks)
3. [Data Concepts](#concepts)
4. [Query Optimsation](#query)

## Data engineering
Data engineering is the processing of designing and constructing data architectures also know as pipelines. It looks at ways to transform raw data into valuable insights through a simple reliable system.
## 1. ETL <a name="etl"></a>
### Ingestion (Extract)
Data ingestion is the process of extracting raw data which can come from various sources such as APIs, Databases, Sensors and file systems.
### Processing (Transform)
Data processing consists of cleaning, formatting and sctructuring data into a desired schema for storage or analysis.
### Storage (Load)
Data is then stored into a database, datawarehouse, datalake or datawarehouse which can then be used for a variety of uses such as analysis or querying.
## 2. Data frameworks <a name="frameworks"></a>
### Apache Hadooop
Apache hadoop is an open source framework for distributed storage and processing using commodity hardware. This provides scalability and fault tolerance.
### Apache Spark
Apache spark is a fast, in memory processing engine that supports batch and real-time data processing. It is fast and easy to use.
## 3. Data concepts <a name="concepts"></a>
### Data modelling
Data modelling is process of designing how the data is structred and related in storage. This invloves creating schemas, relationships, formatting, integer assinging etc. This is important to ensure consistent standardisation through the data which can then be easily processed and stored.
### Data warehousing
Data warehousing involves storing large volumes of structured and semi-structred data into a central reposity which is then used later analysis or querying. Warehouses also consit of marts which are substets of the repositry which store business specific data e.g. sales, finance, banking etc.
#### Solutions:
- Amazon Redshift
- Google BigQuery
- Snowflake
### Data lakes
Data lakes are storage repositories which house huge volumes of semi-structures and raw data and left until it is needed. All data is stored in a single repositry which can be accessed at any time to be used for operations such as advanced analytics, machine leanring and real time analytics.
#### Solutions:
- AWS S3
- Azure data lake
- Databricks
## 4. Query optimisation (queries are written in the most optimal way) <a name="query"></a>
### Indexing 
Indexing is a powerful tool for improving query performance by allowing quick acess to specific data. Indexing is creating indexes which allow for rapid data reterival.
####  - Single-column indexes (assigning indexes on individual columns)
#### - Composite indexes (Indexes on mutliple columns)
#### - Bitmap indexes (Useful for columns with a limited range of distinct values)


