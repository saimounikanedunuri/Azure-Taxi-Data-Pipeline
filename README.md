# NYC Taxi Data Engineering Project 🚖

## 📌 Project Overview
This project demonstrates how to build a **data pipeline using Azure** to process and analyze **NYC Taxi Data**. The goal is to ingest, clean, transform, and analyze taxi trip data to derive useful insights such as **busiest pickup locations, peak ride hours, and average fare per trip**.

## 🏗️ Architecture & Workflow
The project follows the **Medallion Architecture (Bronze → Silver → Gold)** for data processing:

1. **Data Ingestion**: Using **Azure Data Factory (ADF)** to fetch NYC Taxi data from APIs and load it into **Azure Data Lake Storage (ADLS)**.
2. **Data Cleaning & Transformation**: Using **Azure Databricks & PySpark** to remove duplicates, fix missing values, and standardize the dataset.
3. **Data Storage & Versioning**: Processed data is stored in **Delta Lake**, allowing for **time travel and version control**.
4. **Data Analysis & Visualization**: The cleaned data is used in **Power BI** to create dashboards for insights.

## 🔧 Technologies Used
- **Azure Data Lake Storage (ADLS)** – For storing raw and processed taxi trip data.
- **Azure Data Factory (ADF)** – For automating data ingestion from APIs.
- **Azure Databricks & PySpark** – For data transformation and cleaning.
- **Delta Lake** – For efficient data storage, versioning, and time travel.
- **Power BI** – For data visualization and reporting.

## 📂 Data Flow Breakdown
### 1️⃣ Data Ingestion
- Taxi trip records include **pickup & drop-off locations, trip duration, fare amounts, payment types, and ride timestamps**.
- Data is fetched using **ADF Pipelines** and stored in **Azure Data Lake (Bronze Layer)**.

### 2️⃣ Data Processing & Transformation
- **Cleaning:** Fix missing values, remove duplicates, and filter out incorrect fares.
- **Transformation:** Convert trip durations to minutes, standardize column formats, and compute **average fare per mile**.
- **Storage:** Processed data is stored in **Delta Tables (Silver Layer)**.

### 3️⃣ Data Analysis & Insights
- **Busiest pickup locations** (e.g., Times Square, JFK Airport)
- **Peak ride hours** (Morning rush vs. late-night rides)
- **Average fare per trip distance**
- **Trends over different time periods** using **Delta Lake time travel**

## 🚀 Project Implementation Steps
1. **Set up Azure Services**
   - Create an **Azure Resource Group**
   - Set up an **Azure Storage Account** & **Data Lake Storage**
   - Create an **Azure Data Factory** instance
2. **Data Ingestion with ADF**
   - Create a pipeline to pull data from APIs
   - Store raw data in **Azure Data Lake**
3. **Data Processing with Databricks & PySpark**
   - Clean and transform data
   - Store refined data in **Delta Tables**
4. **Data Analysis & Visualization**
   - Query data using **Databricks SQL**
   - Create dashboards in **Power BI**

## 📊 Sample Queries
### 🔹 Get Top 10 Busiest Pickup Locations:
```sql
SELECT pickup_location, COUNT(*) AS trip_count
FROM nyc_taxi_data_silver
GROUP BY pickup_location
ORDER BY trip_count DESC
LIMIT 10;
```

### 🔹 Calculate Average Fare Per Mile:
```sql
SELECT trip_distance, AVG(fare_amount) AS avg_fare
FROM nyc_taxi_data_silver
GROUP BY trip_distance
ORDER BY trip_distance;
```

## 🏆 Key Learnings
- **How to build a cloud-based data pipeline using Azure**
- **Handling real-time and batch data ingestion with ADF**
- **Cleaning and transforming big data using PySpark**
- **Using Delta Lake for data versioning & historical analysis**
- **Creating meaningful visualizations in Power BI**

## 🙌 Acknowledgments
A huge **thank you to Ansh Lamba** for sharing valuable knowledge on Azure Data Engineering! 🚀

## 📌 Next Steps
✅ Optimize pipeline performance using **partitioning & indexing**
✅ Integrate real-time data processing using **Azure Stream Analytics**
✅ Deploy the project as a fully automated **end-to-end Azure solution**

---

💡 If you found this project helpful, feel free to ⭐ **star this repository** and connect with me on **LinkedIn**!

#Azure #DataEngineering #BigData #CloudComputing #NYCTaxiData #Databricks #MicrosoftAzure #Learning

