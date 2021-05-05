# Data-Engineering-Projects
## Project 1 - Data Modeling with Postgres
The objective of this project is to create a SQL analytics database for a fictional music streaming service called Sparkify. The purpose of this database is to enable Sparkify to answer business questions it may have of its users, the types of songs they listen to and the artists of those songs using the data that it has in logs and files. The database provides a consistent and reliable source to store this data.

In this Project:
- The Star Schema optimized for queries was created to ingest data to simplify queries that answers business questions
- An ETL pipeline was built to extract data from .json and .log files, transformed and inserted into Postgres tables using Python and SQL.

## Project 2 - Data Warehousing with AWS Redshift
The objective of this project is to create a data warehouse in the cloud for a fictional music streaming service called Sparkify. Sparkify has grown their user base and song database and want to move their processes and data onto the cloud. 

In this Project, we build an ETL pipeline to extract data stored in .json format in s3 buckets and transforms the data to Warehouse hosted on Amazon Redshift using the AWS SDK for Python

## Data Lake
The objective of this project is to build a Data Lake on AWS cloud using Spark. An ETL pipeline was built that extracts the data from S3, processes it using Spark dataframe and sparkSql, and loads the data back into S3 as a set of dimensional tables in parquet format.
