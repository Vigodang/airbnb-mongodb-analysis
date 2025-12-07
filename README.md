#  Airbnb Data Analytics & Insights (Sydney & Montreal)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![MongoDB](https://img.shields.io/badge/Database-MongoDB_NoSQL-green)
![Jupyter](https://img.shields.io/badge/Tool-Jupyter_Notebook-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

##  Overview
This project provides an in-depth analysis of Airbnb listings in **Sydney (Australia)** and **Montreal (Canada)** using a NoSQL approach. By leveraging **MongoDB** and **Python**, this project explores pricing trends, reviewer behaviors, and geospatial patterns to derive actionable insights for potential hosts and travelers.

This repository serves as a portfolio project demonstrating proficiency in **NoSQL Database Management**, **Complex Aggregation Pipelines**, and **Geospatial Querying**.

---

# MongoDB Big Data Analytics – Retail Transaction Project  
This project demonstrates end-to-end Big Data analytics using **MongoDB**, including:
- Data ingestion of large JSON datasets  
- Cleaning and modelling for document databases  
- Aggregation Framework queries  
- MapReduce operations  
- Exploratory analytics (top-selling products, revenue trends, customer behaviour)

---

## 📌 Project Objectives
- Load and analyse a retail transactions dataset using MongoDB  
- Model data as documents and collections  
- Use Aggregation Pipelines to compute KPIs  
- Compare MapReduce vs Aggregation  
- Produce business insights for retail decision-making  

---

##  Key Features & Technical Highlights

* **Complex Data Aggregation:** Utilized MongoDB's Aggregation Framework (`$match`, `$group`, `$unwind`, `$bucket`) to calculate statistical metrics (min, max, avg prices) across different property types.
* **Geospatial Analysis:** implemented `$geoNear` to filter and sort listings within a 5km radius of major landmarks (e.g., Sydney Opera House).
* **Text & Regex Search:** Performed text pattern matching to identify specific amenities and clean user review data.
* **Data Cleaning & Transformation:** Handled missing values, renamed fields for clarity, and transformed unstructured JSON data into structured insights.
* **Performance Optimization:** Efficient querying using indexing and limit operations on large datasets.

---

##  Repository Structure

```text
airbnb-mongodb-analysis/
├── notebooks/
│   └── Airbnb_Sydney_Montreal_Analysis_MongoDB.ipynb  # Main analysis notebook
├── README.md                         # Project documentation
└── requirements.txt                  # Python dependencies


