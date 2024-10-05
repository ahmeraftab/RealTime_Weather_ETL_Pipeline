# Weather Data ETL Pipeline

This project implements a comprehensive ETL (Extract, Transform, Load) pipeline using the **OpenWeatherMap API**, **Apache Airflow**, **Amazon S3**, and **Snowflake**. The pipeline efficiently extracts real-time weather data, processes it, and loads it into Snowflake for analysis and querying.

## Key Features

- **Data Extraction**: Retrieves real-time weather data from OpenWeatherMap.
- **API Validation**: Ensures the OpenWeatherMap API is operational through an Airflow DAG.
- **Data Storage**: Stores raw weather data in an S3 bucket.
- **Data Transformation**: Processes the data in a separate Airflow DAG.
- **Data Loading**: Loads the transformed data into Snowflake via an automated Snowpipe.

## Technology Stack

- **OpenWeatherMap API**: Source for real-time weather data.
- **Apache Airflow**: Manages the ETL process with three distinct DAGs:
  - **DAG 1**: Validates the API's functionality.
  - **DAG 2**: Extracts and stores raw data in S3.
  - **DAG 3**: Transforms the data and triggers Snowpipe to load data into Snowflake.
- **Amazon S3**: Stores raw weather data.
- **Snowflake**: Serves as the data warehouse for storing and analyzing weather data.
- **Snowpipe**: Automates data ingestion from S3 into Snowflake tables.

## Workflow Overview

1. **Extract**: A DAG extracts real-time weather data from OpenWeatherMap in JSON format.
2. **API Health Check**: The first DAG ensures the API is functioning properly before continuing.
3. **Transform**: Another DAG transforms the raw data into an analytics-ready format.
4. **Load**: The transformed data is uploaded to an S3 bucket, triggering Snowpipe to ingest it into Snowflake.
5. **Querying**: Once in Snowflake, users can run queries for weather data analysis.

![Weather Data ETL Pipeline](https://github.com/user-attachments/assets/08d61b3f-3ebb-4a8b-a9a3-11a4d23da6e9)

--- 

This version includes the link to the image from the attachment.
