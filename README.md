Serverless Data Pipeline for CSV Processing on AWS
📌 Project Overview

This project implements a fully automated, serverless data pipeline on AWS to ingest, clean, transform, and visualize CSV data.
The pipeline uses event-driven architecture to process files with minimal manual intervention and produces interactive dashboards for analysis.

The solution is designed to reflect real-world data engineering workflows, focusing on scalability, automation, and cloud-native best practices.


🏗️ Architecture Overview

The pipeline follows a multi-stage architecture:

Raw CSV files are uploaded to an Amazon S3 (Raw Bucket)

S3 event notifications trigger an AWS Lambda function

Lambda preprocesses and cleans the CSV data

Cleaned data is stored in an S3 Processed Bucket

AWS Glue Crawler detects schema and updates the Glue Data Catalog

AWS Glue ETL Job transforms data and writes curated output

Final data is stored in an S3 Final Bucket

Amazon QuickSight visualizes the final dataset using dashboards


🔧 Services Used

Amazon S3 – Storage for raw, processed, and final datasets

AWS Lambda – Serverless preprocessing of CSV files

AWS Glue – Schema discovery, ETL, and Data Catalog

Amazon QuickSight – Data visualization and dashboarding

AWS IAM – Secure role-based access control


⚙️ Project Workflow
Step 1: Data Ingestion

CSV files are uploaded to a designated folder in the raw S3 bucket

S3 triggers a Lambda function automatically on file upload

Step 2: Data Preprocessing (Lambda)

Reads CSV files from S3

Removes rows with missing values

Writes cleaned data to the processed S3 bucket

Step 3: Data Transformation (AWS Glue)

Glue Crawler scans processed data and infers schema

Metadata is stored in the Glue Data Catalog

Glue ETL job performs transformations and loads curated data into the final S3 bucket

Step 4: Data Visualization (QuickSight)

QuickSight connects to the final S3 dataset using a manifest file

Interactive dashboards are created for insights and analysis


🔐 Security & Access Management

IAM roles configured for Lambda, Glue, and QuickSight

Services follow least-privilege access principles

Secure service-to-service communication enabled via IAM policies


🧠 Key Concepts Demonstrated

Serverless architecture

Event-driven data pipelines

ETL (Extract, Transform, Load)

Data cataloging and schema inference

Cloud-based data visualization


🚀 How to Run This Project

Create three S3 buckets:

raw-data

processed-data

final-data

Configure IAM roles for Lambda and Glue

Deploy the Lambda function and attach S3 triggers

Upload CSV files to the raw bucket

Run Glue Crawler and ETL job

Connect Amazon QuickSight to the final dataset

Build dashboards and analyze insights


📈 Output

Automated CSV data processing

Cleaned and transformed datasets

Interactive dashboards in Amazon QuickSight


🧩 Future Enhancements

Add Amazon Athena for SQL-based querying

Implement data quality checks

Add workflow orchestration using AWS Step Functions

Store transformed data in Parquet format for better performance


📚 Learning Outcome

This project strengthened my understanding of AWS data engineering services, serverless pipelines, and real-world ETL workflows used in production data platforms.
