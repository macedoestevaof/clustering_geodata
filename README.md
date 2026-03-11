# Clustering and Analysis of Geospatial Logistics Data

This project explores **logistics analysis** and **geospatial clustering** for delivery operations in India. It covers **DBSCAN clustering**, geospatial cleaning, flow classification, and insights into economic hubs and delivery patterns. Overall, it demonstrates how clustering, geospatial cleaning, and flow classification provide actionable insights into logistics operations and support the optimization of *Last-Mile* delivery strategies in India.

---

## 1. Geographical Logistics Data

This section presents an exploratory and technical analysis of a **logistics (delivery) dataset** in India, focusing on spatial patterns, cleaning geographical anomalies, and validating *Last-Mile* delivery strategies.

### 1.1 Volume and Data Quality
The delivery dataset contains **43,739 records**, fully numerical (`float64`) with **no null values**. However, visual inspection reveals **critical geographical inconsistencies**:

- **Geospatial Cleaning:** Some latitudes, e.g., **-30.90**, are invalid since India lies entirely above **8° N**, indicating input errors.  
- **Anomaly Detection:** About **3,693 records (8.4%)** were located in oceanic areas or near zero, which could distort clustering algorithms if not sanitized.

The geographic data was then cleaned and prepared. Latitude and longitude coordinates for stores, drop-offs, and cluster centroids were analyzed to ensure **accurate city assignment**. Optional **map visualizations** were created using **Cartopy**, including country and state boundaries when shapefiles were available.

### 1.2 Market Diagnosis and Economic Hubs
Analysis shows dominance of **economic hubs**, with concentration in **Maharashtra** and **Karnataka** (over 6,000 deliveries each), reflecting the importance of **Mumbai** and **Bengaluru**.  

The logistics network aligns with **population density**: the top cities have populations between **8–12 million**, and **low radial distances** between origin and destination points confirm **intra-municipal flows** and a highly capillary *Last-Mile* strategy.

### 1.3 Demand Dynamics and Mid-Sized Centers
Logarithmic scale analysis highlights **non-linear demand relative to population size**:

- **Key Finding:** A cluster of mid-sized cities (**10⁵–10⁶ inhabitants**) shows delivery volumes rivaling large metropolises.  
- **Operational Impact:** Cities with similar population sizes can have very different delivery volumes, indicating that **local infrastructure and proximity to distribution centers** influence operational success more than population alone.

---

## 2. Clustering on Geographic Data

This section focuses on **clustering and analysis of geographic data** using **DBSCAN**, including city assignments and flow type classification. It demonstrates how to identify clusters of locations, assign the nearest cities, and classify delivery flows based on geographic proximity.

### 2.1 Algorithm Overview
The algorithm applies the **DBSCAN algorithm** with **Haversine distance** and a **Ball Tree structure** to geospatial data. It effectively identifies clusters of coordinates, allowing mapping of stores and drop-off locations to their nearest cities. Each delivery is classified into one of three flow types:

- **Intramunicipal:** Same city  
- **Intrastate:** Same state, different cities  
- **Interstate:** Different states  

### 2.2 Analysis Insights

![Visualizing Points, Clusters, and Related Cities on the Map.png](https://github.com/macedoestevaof/clustering_geodata/blob/main/Visualizing%20Points%2C%20Clusters%2C%20and%20Related%20Cities%20on%20the%20Map.png)

DBSCAN successfully identified clusters based on geographic coordinates. Some **misclassifications** occurred due to limitations in the city reference dataset, for example, **Belgaum** was incorrectly assigned as the nearest city to a coastal region. Overall, the clustering results were satisfactory but dependent on the **quality and completeness** of reference data.

---

### Technologies Used
- **Python:** Core processing and analysis  
- **Pandas & NumPy:** Data manipulation and cleaning  
- **Matplotlib & Seaborn:** Visualization (scatter plots, logarithmic scales)  
- **DBSCAN:** Clustering algorithm for identifying patterns and outliers

### Data Sources and Contributors
- [Top 500 Indian Cities](https://www.kaggle.com/datasets/zed9941/top-500-indian-cities) by Arijit Mukherjee  
- [Amazon Delivery Dataset](https://www.kaggle.com/datasets/sujalsuthar/amazon-delivery-dataset) by Sujal Suthar

### Authors

- **Estevão Macedo** *(Geospatial clustering)*  
  - [LinkedIn](https://www.linkedin.com/in/estevaomacedo/)  
  - [GitHub](https://github.com/macedoestevaof)  

- **Samuel Origa** *(Logistics analysis)*  
  - [LinkedIn](https://www.linkedin.com/in/samueloriga/)  
  - [GitHub](https://github.com/samuel98575/)  
