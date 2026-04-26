# 🚀 End-to-End Batch Data Pipeline (PySpark + Data Lake + Great Expectations)

## 📌 Project Overview
This project implements a complete **data engineering batch pipeline** using modern big data tools. It simulates a real-world data lake architecture with Bronze, Silver, and Gold layers.

The pipeline processes NYC Taxi Trip data and transforms raw data into analytics-ready datasets.

---

## 🏗️ Architecture

### 🥉 Bronze Layer (Raw Data)
- Ingests raw NYC Taxi dataset (Parquet format)
- Stores data without modification

### 🥈 Silver Layer (Cleaned Data)
- Removes duplicates
- Filters invalid records (negative fares, invalid distances)
- Prepares clean dataset for processing

### 🥇 Gold Layer (Analytics Data)
- Aggregates business KPIs:
  - Total trips per day
  - Total revenue per day
  - Average fare per trip
- Stores partitioned Parquet files for analytics

---

## ⚙️ Tech Stack

- PySpark (Distributed Data Processing)
- Parquet (Columnar Storage Format)
- Python
- Great Expectations (Data Quality Validation)
- Google Colab (Execution Environment)

---

## 📊 Dataset

NYC Yellow Taxi Trip Data (Public Dataset)

Source:
https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

---

## 🔄 Pipeline Flow

1. **Data Ingestion**
   - Load raw dataset into Spark

2. **Bronze Layer**
   - Store raw data in data lake format

3. **Silver Layer**
   - Clean data
   - Remove duplicates
   - Filter invalid values

4. **Gold Layer**
   - Aggregate metrics:
     - Trips per day
     - Revenue per day
     - Average fare
   - Partitioned storage for analytics

5. **Data Quality Checks**
   - Validate schema using Great Expectations
   - Check missing values and value ranges

---

## 🧪 Data Quality Rules

- fare_amount must be > 0
- trip_distance must be within valid range
- No null values in critical columns

---

## ▶️ How to Run

### Step 1: Install dependencies
bash
pip install pyspark great_expectations pandas

### Step 2: Run notebook

Open Google Colab and execute pipeline step-by-step.

### Step 3: Output layers

Check generated folders:

/bronze
/silver
/gold

### 📈 Output Examples
Daily trip counts
Revenue trends
Average fare per trip
Clean validated dataset

---

### 🔁 Workflow Summary

Raw Data → Bronze → Silver → Gold → Analytics Dashboard Ready

---

### 📌 Key Features

- ✔ End-to-end batch pipeline
- ✔ Data lake architecture (Medallion model)
- ✔ Data cleaning & transformation with PySpark
- ✔ Data quality validation with Great Expectations
- ✔ Partitioned analytics output
- ✔ Airflow-style orchestration (simulated)

---

### 🚀 Future Improvements
Integrate real Apache Airflow DAGs
Store data in AWS S3 instead of local storage
Add Power BI dashboard on Gold layer
Deploy as scheduled pipeline
