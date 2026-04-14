# 📊 UPI Transactions Data Warehouse & ETL Pipeline

## 📌 Project Overview

This project focuses on the **design and implementation of a Data Warehouse** for UPI (Unified Payments Interface) transactions using an ETL pipeline.

The solution integrates data from multiple sources, processes it through a staging layer, and loads it into a structured **star schema** for analytical purposes.

---

## 🎯 Objectives

* Design a **data warehouse architecture**
* Implement **ETL pipelines using SSIS**
* Transform raw OLTP data into **analytical data**
* Support **business intelligence and reporting**

---

## 📂 Dataset

* Source: Kaggle (UPI Transactions Dataset)
* Records: ~250,000 transactions
* Type: OLTP dataset (transaction-level data)

---

## 🏗️ System Architecture

The solution follows a **3-layer architecture**:

1. **Source Layer**

   * CSV files (UPI transactions, completion data)
   * Excel (merchant mapping)
   * SQL Server (bank data)

2. **Staging Layer (UPI_Staging)**

   * Stores raw and cleaned data
   * Handles validation and deduplication

3. **Data Warehouse Layer (UPI_DW)**

   * Star schema design
   * Optimized for analytics

---

## ⭐ Data Warehouse Design

### 🔹 Fact Table

**FactUPITransactions**

* Stores transaction-level data
* Includes:

  * Transaction amount
  * Fraud flag
  * Transaction status
  * Processing time

### 🔹 Dimension Tables

* Dim_Date
* Dim_Merchant
* Dim_Bank
* Dim_Channel
* Dim_CustomerProfile

---

## 🔄 ETL Process

### 📦 Package 1: Staging Load

* Load CSV → Staging Database
* Data cleaning and validation

### 📦 Package 2: Data Warehouse Load

* Populate dimension tables
* Load fact table with surrogate keys

### 📦 Package 3: Accumulating Fact Update

* Updates transaction completion time
* Calculates processing duration

---

## 🔁 ETL Execution Order

1. Load Staging Data
2. Load DimDate
3. Load DimMerchant
4. Load DimBank
5. Load DimChannel
6. Load DimCustomerProfile
7. Load Fact Table

---

## 🧠 Key Concepts Used

* Data Warehousing
* Star Schema
* ETL (Extract, Transform, Load)
* SSIS Packages
* Slowly Changing Dimensions (SCD)
* Accumulating Fact Table

---

## 🛠️ Technologies Used

* Microsoft SQL Server
* SQL Server Integration Services (SSIS)
* Visual Studio
* CSV / Excel Data Sources

---

## 📊 Features

* Handles large dataset (250K+ records)
* Supports analytical queries
* Tracks transaction lifecycle
* Ensures data integrity and consistency

---

## ⚠️ Assumptions

* Transaction IDs are unique
* Source data is valid and clean
* Completion data is partially available
* Dimension data is mostly static

---

## ✅ Conclusion

This project demonstrates a complete **end-to-end Data Warehouse solution**, including data extraction, transformation, loading, and analytical modeling for UPI transaction data.

---

## 👩‍💻 Author

**Nadali Devindi**

SLIIT – Data Warehousing & Business Intelligence

---
