# Clustering on Geographic Data (clustering_geodata)

Clustering and analysis of geographic data using **DBSCAN**, including city assignments and flow type classification. This project demonstrates how to identify clusters of locations, assign the nearest cities, and classify delivery flows based on geographic proximity.

## Project Overview

The project focuses on applying the **DBSCAN algorithm** with **Haversine distance** and a **Ball Tree structure** to geospatial data. The algorithm effectively identifies clusters of coordinates, allowing us to map stores and drop-off locations to their nearest cities. Each delivery is then classified into one of three flow types: **Intramunicipal** (same city), **Intrastate** (same state, different cities), or **Interstate** (different states).

## Data Processing

Before clustering, the geographic data is cleaned and prepared. Latitude and longitude coordinates for stores, drop-offs, and cluster centroids are analysed to ensure accurate assignment. Additionally, optional map visualizations are created using **Cartopy** to plot stores, drop-offs, and cluster centers, including boundaries of countries and states when shapefiles are available.

## Analysis Insights

![Visualizing Points, Clusters, and Related Cities on the Map.png](https://github.com/macedoestevaof/clustering_geodata/blob/main/Visualizing%20Points%2C%20Clusters%2C%20and%20Related%20Cities%20on%20the%20Map.png)

The map visualization showed that DBSCAN performed well in identifying clusters based on geographic coordinates. However, limitations in the city reference dataset led to some misclassifications. For example, **Belgaum** was incorrectly assigned as the nearest city to a coastal region due to insufficient geographic coverage. Overall, the clustering results were satisfactory but dependent on the quality and completeness of the reference data.

Interestingly, the example dataset contained **only intramunicipal flows**, which simplified the analysis. This scenario may differ in datasets with more diverse flows, providing an opportunity to explore how the algorithm behaves with different spatial distributions. Users are encouraged to experiment with their own data to see how flow classifications change.

## Saving Enriched Data

After completing the clustering and flow type classification, the enriched dataset is saved for further use. This dataset can be used for additional analysis, visualization, or as a foundation for data enrichment in other geospatial projects. By combining clustering, city assignment, and flow classification, this project provides a practical workflow for geospatial data analysis using DBSCAN.

## Acknowledgements

We would like to thank the authors of the publicly available datasets used in this project:

- [Top 500 Indian Cities](https://www.kaggle.com/datasets/zed9941/top-500-indian-cities) by Arijit Mukherjee
- [Amazon Delivery Dataset](https://www.kaggle.com/datasets/sujalsuthar/amazon-delivery-dataset) by Sujal Suthar  
