# Real-Time Data Pipeline for NYC Yellow Taxi Trips

## Project Overview

This project is designed to build a **real-time data pipeline** for processing and analyzing NYC Yellow Taxi trips data from **January 2024 to June 2024**. The dataset contains approximately **21 million rows**. The pipeline leverages streaming and batch processing technologies to ingest, process, transform, and store the data for analytical use.

The pipeline is implemented using:
- **Python** for data downloading and Kafka production.
- **Apache Kafka** for real-time data ingestion.
- **Spark Streaming** for consuming and processing data.
- **MySQL** for storing raw data as a staging layer.
- **PySpark** for data cleaning, transformation, and normalization.
- **Hive** for creating a normalized **Star schema** data warehouse.
- **Power BI** for data analysis and visualization.

## Architecture

### Pipeline Flow:

1. **Data Ingestion**:
   - A Python application automatically downloads NYC Yellow Taxi trips data and pushes it to an Apache Kafka topic at a rate of **500 rows every 10 seconds**.
   - Apache Kafka handles the stream of raw data, ensuring real-time data ingestion.

2. **Data Streaming and Staging**:
   - Spark Streaming reads data from the Kafka topic in real time.
   - Data is processed in batches and written to a **MySQL** database in **denormalized** format, serving as the **staging layer**.

3. **Data Cleaning and Transformation**:
   - A PySpark application is responsible for cleaning the raw data, handling null values, outliers, and ensuring data quality.
   - The cleaned data is transformed into a **Star schema** and stored in **Hive** for efficient querying and analysis.

4. **Data Analysis and Visualization**:
   - Using **Power BI**, insights are derived from the Hive warehouse, including key metrics like trip duration, fare amounts, trip distance, and more.


































https://github.com/user-attachments/assets/d56453d7-e9bc-4084-b30a-9e703258aac6
