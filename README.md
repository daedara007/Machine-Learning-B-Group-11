# Real Estate Market Segmentation in Balikpapan: K-Means vs DBSCAN

Group 11 - Machine Learning Class B
Institut Teknologi Kalimantan (ITK)

Team Members:
- Kevin Jonathan Wijaya
- Fauzan Fayzul Haq
- Vivian Marsyanda

## Project Overview
This repository contains the source code for our comparative analysis of K-Means and DBSCAN clustering algorithms. The objective of this study is to segment the real estate market in Balikpapan City to understand its submarket structure, especially considering the rapid spatial and economic changes driven by the new capital city (IKN) development.

Features used for the clustering models:
1. Lokasi_Num (Categorical encoding of districts)
2. Harga_Num (Property price)
3. LT_Num (Land area in m2)
4. LB_Num (Building area in m2)
5. Bedroom_Num (Number of bedrooms)
6. Bathroom_Num (Number of bathrooms)
7. Harga_per_m2 (Price per square meter)

## Methodology
- K-Means: The optimal number of clusters was determined using the Elbow Method (k=4).
- DBSCAN: The parameters were set to MinPts=14 (based on the rule of thumb 2 * features) and Epsilon was determined using a K-Distance plot with a 97th-percentile pruning technique to handle global noises.

## Key Findings
Both models were evaluated using the Silhouette Coefficient and Davies-Bouldin Index (DBI).

- K-Means (k=4)
  Silhouette Score: 0.7181 | DBI: 0.4920
  Result: Successfully delineated 4 macro-level submarkets but forced extreme outliers into standard clusters, which blurred true market boundaries.

- DBSCAN
  Silhouette Score: 0.8081 | DBI: 0.2855
  Result: Isolated 96 extreme outlier properties as noise (label -1) and successfully uncovered a smaller entry-level housing segment in East Balikpapan.

Conclusion: DBSCAN proved to be the more robust algorithm for mapping the submarkets because it handles extreme price anomalies without distorting the core market segments.
