

# Project Name: YouTube Data Analytics on AWS Platform

[![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-orange?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/lambda/)
[![AWS S3](https://img.shields.io/badge/AWS-S3-blue?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/s3/)
[![AWS Glue](https://img.shields.io/badge/AWS-Glue-lightgrey?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/glue/)
[![AWS Glue Studio](https://img.shields.io/badge/AWS-Glue_Studio-lightgrey?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/glue/)
[![Amazon QuickSight](https://img.shields.io/badge/Amazon-QuickSight-yellow?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/quicksight/)
[![AWS CLI](https://img.shields.io/badge/AWS-CLI-black?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/cli/)
[![Amazon Athena](https://img.shields.io/badge/Amazon-Athena-lightblue?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/athena/)
[![AWS Glue Crawler](https://img.shields.io/badge/AWS-Glue_Crawler-lightgrey?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/glue/)
[![PySpark](https://img.shields.io/badge/PySpark-yellow?logo=apache-spark&logoColor=white)](https://spark.apache.org/docs/latest/api/python/)
[![AWS Glue DataBrew](https://img.shields.io/badge/AWS-Glue_DataBrew-lightgrey?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/glue/data-brew/)
[![AWS Glue DynamicFrame](https://img.shields.io/badge/AWS-Glue_DynamicFrame-lightgrey?logo=amazon-aws&logoColor=white)](https://aws.amazon.com/glue/)



## Table of Contents

# Project Name: YouTube Data Analytics on AWS Platform

![AWS Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/AWS_Simple_Icons_AWS_Cloud.svg/200px-AWS_Simple_Icons_AWS_Cloud.svg.png)

## Table of Contents
- [Overview](#overview)
- [Prerequisites and Setup](#prerequisites-and-setup)
- [Data Processing](#data-processing)
   - [1. Uploading Raw Data to S3 Buckets](#1-uploading-raw-data-to-s3-buckets)
   - [2. Creating IAM Role](#2-creating-iam-role)
   - [3. AWS Glue Catalog](#3-aws-glue-catalog)
   - [4. JSON File Serialization and Deserialization](#4-json-file-serialization-and-deserialization)
   - [5. Converting JSON to Apache Parquet](#5-converting-json-to-apache-parquet)
   - [6. AWS Lambda Function Configuration](#6-aws-lambda-function-configuration)
   - [7. Data Cleaning](#7-data-cleaning)
   - [8. Creating a New Bucket](#8-creating-a-new-bucket)
- [ETL Pipeline and Analytics](#etl-pipeline-and-analytics)
   - [1. ETL Job](#1-etl-job)
   - [2. Triggering Lambda Function](#2-triggering-lambda-function)
   - [3. Data Cleanup](#3-data-cleanup)
   - [4. Building Analytics Pipeline](#4-building-analytics-pipeline)
   - [5. Analytic Data Storage](#5-analytic-data-storage)
   - [6. Creating Analytics Database](#6-creating-analytics-database)
   - [7. Quicksight Dashboard](#7-quicksight-dashboard)
- [Conclusion](#conclusion)

## Overview
This project focuses on performing YouTube data analytics using the AWS platform. The goal is to extract insights from a raw dataset consisting of unstructured JSON and CSV files and create a comprehensive analytics report. The project involves various steps, including data processing, conversion, cleaning, and building an analytics pipeline. 


## Data Processing

### 1. Uploading Raw Data to S3 Buckets
Used the AWS CLI to upload the raw JSON and CSV files to AWS S3 Buckets.

### 2. Creating IAM Role
Set up an IAM role for the project with the necessary permissions, including S3 admin access and Glue service access roles.

### 3. AWS Glue Catalog
Utilized the AWS Glue Catalog to perform data processing tasks. Created a database in the catalog and ran a crawler to generate a data catalog from the uploaded files.

### 4. JSON File Serialization and Deserialization
Implemented the serialization and deserialization process to convert the unstructured JSON files into a tabular format for easier analysis.

### 5. Converting JSON to Apache Parquet
Developed an AWS Lambda function using Python to convert the processed JSON files into Apache Parquet format. Tested the function to ensure its functionality.

### 6. AWS Lambda Function Configuration
Created a new role with the necessary permissions and configure the AWS Lambda function. Add the AWS Data Wrangler layer to the Lambda code for improved functionality.

### 7. Data Cleaning
Utilized Athena to query and clean the converted JSON data. Identify and handle any missing values, outliers, or inconsistencies to ensure data quality.

### 8. Creating a New Bucket
Set up a new bucket for data processing, including schema conversion and partition key configuration. Created a database within the AWS Data Catalog for the cleaned data.

## ETL Pipeline and Analytics

### 1. ETL Job
Developed an ETL job using PySpark scripts on AWS Glue to convert all the raw files (CSV and JSON) into the desired output schema. Configured the necessary script for partition keys.

### 2. Triggering Lambda Function
Added a trigger to the Lambda function to automatically execute whenever new JSON data is uploaded to the S3 raw file bucket. This ensures continuous data processing.

### 3. Data Cleanup
Deleted the raw JSON files from the S3 bucket to allow for a fresh upload of data using the AWS CLI.

### 4. Building Analytics Pipeline
Utilized AWS Glue Studio to construct an analytics report layer. Join the relevant tables using an inner join based on the category_id and id columns.

### 5. Analytic Data Storage
Created a new bucket to store the analytic data in the Parquet format with Snappy compression for improved efficiency.

### 6. Creating Analytics Database
Established a new database within the AWS Data Catalog specifically for the analytic table. Set appropriate partition keys for efficient data retrieval.

### 7. Quicksight Dashboard
Signed up for Amazon Quicksight and build a dataset using the S3 source and Athena. Selected the relevant database and construct a dashboard to visualize the data and gain valuable insights.

## Conclusion
By following the detailed steps outlined above, you will be able to perform YouTube data analytics using the AWS platform. This project showcases the use of various AWS services, such as S3, Glue, Lambda, Athena, and Quicksight, to process, clean, transform, and visualize the data. The end result is a comprehensive analytics report that provides valuable insights into the YouTube dataset.

...
