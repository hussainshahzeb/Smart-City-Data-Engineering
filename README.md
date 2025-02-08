# Smart-City-Data-Engineering

## Project Overview
This project builds a real-time data streaming pipeline for a **Smart City** initiative. It captures and processes real-time data from a vehicle traveling from **London to Birmingham**, including:

- Vehicle data  
- GPS data  
- Emergency incidents  
- Weather conditions  
- Camera footage  

The pipeline leverages **IoT devices, Apache Kafka, Apache Spark, Docker, and AWS services** to ensure efficient data ingestion, processing, storage, and visualization.

---

## Architecture Overview

### Technologies Used
- **IoT Devices**: Capture real-time data  
- **Apache Zookeeper**: Manages and coordinates Kafka brokers  
- **Apache Kafka**: Real-time data ingestion  
- **Apache Spark**: Real-time data processing & streaming  
- **Docker**: Containerization & orchestration  
- **Python**: Data processing scripts  
- **AWS Cloud Services**:
  - **S3**: Stores processed data as Parquet files  
  - **Glue**: Extracts & catalogs data  
  - **Athena**: Queries processed data  
  - **IAM**: Manages access & permissions  
  - **Redshift**: Data warehousing & analytics  
  - **Amazon QuickSight**: Data visualization & dashboards  

---

## Project Workflow

### 1. Data Ingestion  
- IoT devices capture real-time data.  
- Data is ingested into **Kafka topics** using `docker-compose.yml`.  

### 2. Data Processing  
- Apache Spark reads data from Kafka topics.  
- Spark processes & writes data to **AWS S3** as Parquet files.  
- Spark Streaming ensures real-time data processing.  

### 3. Data Storage  
- Processed data is stored in **AWS S3**.  
- AWS Glue crawlers extract & catalog the data.  

### 4. Data Querying  
- AWS Athena queries the processed & cataloged data.  

### 5. Data Visualization  
- **Amazon QuickSight** visualizes the queried data with interactive dashboards.  

---

## Getting Started

### Prerequisites
- Docker & Docker Compose  
- AWS Account with **IAM roles & permissions**  
- Python 3.x  
- Apache Kafka & Apache Spark setup  

### Setup Instructions

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/user/repo.git
   cd smart-city-pipeline
   ```

2. **Configure Docker**:
   - Ensure Docker and Docker Compose are installed and running.
   - Configure Kafka and Spark in `docker-compose.yml`.
   - Start the services:
     ```sh
     docker-compose up -d
     ```

3. **AWS Configuration**:
   - Set up AWS IAM roles and permissions.
   - Configure AWS S3 buckets, Glue crawlers, and Athena.
   - Update the configuration files with your AWS credentials and resource details.

4. **Run Data Ingestion**:
   - Start producing data to Kafka topics using IoT data simulators.

5. **Run Spark Streaming**:
   - Submit the Spark job to process and stream data to S3:
     ```sh
     spark-submit --master local[2] your-spark-job.py
     ```

6. **Query Data with Athena**:
   - Use AWS Athena to query the processed data stored in S3.

7. **Visualize Data with QuickSight**:
   - Create an Amazon QuickSight analysis and build your dashboard with the processed data.


## Conclusion

This project demonstrates the power of modern data engineering tools to handle complex, real-time data streams and deliver actionable insights for Smart City initiatives. The use of AWS services ensures scalability, reliability, and ease of data management, making it an excellent example of an end-to-end data streaming pipeline.
