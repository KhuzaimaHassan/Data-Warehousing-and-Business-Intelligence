# 📦 Unified E-commerce Analytics

### *A Data Warehouse for Integrated Sales & Product Insights*

## 📘 Course Information

* **Course:** CT-472 Data Warehousing & Business Intelligence
* **Institution:** NED University of Engineering & Technology
* **Department:** Computer Science & IT
* **Program:** FYDS (Specialization in Data Science)

---

## 👥 Team Members

* **Ebaad Khan** (DT-22045)
* **Ezaan Khan** (DT-22046)
* **Syed Ahmed Ali** (DT-22301)
* **Muhammad Khuzaima Hassan** (DT-22302)

---

## 🎯 Project Overview

Modern e-commerce platforms often suffer from **data silos** where customer, sales, and product information are stored in separate systems that do not communicate. This project solves that issue by developing a fully implemented **Sales Data Warehouse**.

The solution includes:

* A **robust ETL pipeline** (Python + SQLAlchemy)
* A clean **Star Schema**
* Cloud deployment on **Aiven PostgreSQL**
* Interactive **Power BI dashboards**
* **Customer segmentation** using K-Means (RFM)

The goal is to deliver **unified insights** into sales performance, customer behavior, and profitability.

---

## 🏗️ Data Warehouse Architecture

The project uses a **Hybrid Architecture**, combining on-premise sources and cloud-hosted analytics.

### **Architecture Layers**

1. **Source Layer**
   OLTP databases, CSV files, and REST APIs.

2. **Staging Layer**
   Data cleansing, deduplication, validation, and standardization.

3. **Data Warehouse Layer (Core)**
   PostgreSQL database using a **Star Schema** for OLAP queries.

4. **Presentation Layer**
   Power BI dashboards and downstream analytics.

---

## 🌟 Star Schema Design

### **Fact Table**

* `fact_sales`
  Contains metrics such as `price`, `quantity`, `profit_margin`, `discount`, and foreign keys.

### **Dimension Tables**

* **dim_customer** – Customer demographics (age, gender, region)
* **dim_date** – Date hierarchy (day, month, quarter, year)
* **dim_product_sales** – Product metadata (category, sub-category, brand)

---

## ⚙️ ETL Workflow (Python)

The pipeline was developed in Google Colab and follows:

### **1. Extract**

* Read CSV files, RestAPI's and OLTP data using Pandas + SQLAlchemy.

### **2. Transform**

* Handle nulls and incorrect values
* Standardize categorical fields
* Remove duplicates
* Apply business rules (e.g., computing profit margin)
* Generate surrogate keys for dimensional modeling

### **3. Load**

* Load dimension tables first
* Load fact table ensuring referential integrity
* Deploy final schema into Aiven PostgreSQL

---

## 🛠️ Technology Stack

| Component                 | Tool                        | Purpose                   |
| ------------------------- | --------------------------- | ------------------------- |
| **Data Storage**          | PostgreSQL (Aiven Cloud)    | Core DW                   |
| **ETL & Transformation**  | Python (Pandas, SQLAlchemy) | Data ingestion & cleaning |
| **Business Intelligence** | Power BI                    | Dashboards & visuals      |
| **ML & Analytics**        | Python (Scikit-learn)       | RFM Segmentation          |
| **DB Admin**              | pgAdmin                     | Management & queries      |
| **Modeling**              | Power BI Model View         | Schema visualization      |

---

## 📊 Analytics & Key Insights

### **1. Power BI Dashboard (Descriptive Analytics)**

Key insights discovered:

* **Top Category:** Electronics (57% of total revenue)
* **Seasonality:** Sales peak during **May–August**
* **Payment Trends:** Highest usage: **Credit Card** and **COD**
* **Customer Demographics:** Higher purchase activity from **18–35 age group**
* **Profitability:** Discount strategy positively correlates with profit trends

---

## 🔬 2. Advanced Analytics – RFM Customer Segmentation (K-Means)

### **Segments Identified**

| Cluster | Name             | Recency          | Frequency | Monetary      | Interpretation               |
| ------- | ---------------- | ---------------- | --------- | ------------- | ---------------------------- |
| **0**   | At-Risk / Lapsed | High recency     | Low freq  | Low value     | Need win-back campaigns      |
| **1**   | Loyal Customers  | Moderate recency | High freq | Highest value | Engage to avoid churn        |
| **2**   | Champions / VIPs | Low recency      | High freq | High value    | Reward with loyalty programs |

---

## 🏁 Conclusion

The project demonstrates a complete **end-to-end Data Warehouse implementation**, covering:

* Source extraction
* Data transformation
* Dimensional modeling
* Cloud deployment
* BI reporting
* Machine learning analytics

This unified architecture enables both **"What happened?"** (descriptive analytics) and **"Who are our customers?"** (segment analysis), forming a foundation for future predictive modeling such as churn prediction and sales forecasting.
