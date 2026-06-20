# 🏡 Real Estate Market Segmentation in Balikpapan: K-Means vs DBSCAN

**Group 11 — Machine Learning Class B** Institut Teknologi Kalimantan (ITK)

**Team Members:**
* Kevin Jonathan Wijaya 
* Fauzan Fayzul Haq 
* Vivian Marsyanda 

---

## 📌 Project Overview
The relocation of Indonesia's capital city (IKN) to East Kalimantan has triggered rapid economic and spatial transformations, significantly impacting the local real estate market. This project conducts a comparative analysis between **K-Means** (centroid-based) and **DBSCAN** (density-based) clustering algorithms to accurately segment the housing market in Balikpapan City. 

The goal of this study is to discover hidden submarkets and evaluate how each algorithm handles extreme price anomalies in a highly dynamic real estate environment.

## 📊 Dataset
The dataset comprises approximately 1,200 active residential property listings scraped from `rumah123.com`. 
* **Preprocessing:** The raw data underwent missing value handling, duplicate removal, numerical scaling (Min-Max Normalization), and categorical encoding for locations.
* **Features used for clustering (7 variables):**
  1. `Lokasi_Num` (Categorical Encoding of Districts)
  2. `Harga_Num` (Property Price)
  3. `LT_Num` (Land Area in m²)
  4. `LB_Num` (Building Area in m²)
  5. `Bedroom_Num` (Number of Bedrooms)
  6. `Bathroom_Num` (Number of Bathrooms)
  7. `Harga_per_m2` (Engineered feature: Price per square meter)

## ⚙️ Methodology & Algorithms
* **K-Means:** Optimized at **k = 4** (determined via the Elbow Method).
* **DBSCAN:** Optimized with **MinPts = 14** (Rule of thumb: $2 \times 7$ features) and **Epsilon ($\epsilon$)** determined using a K-Distance plot with a 97th-percentile pruning technique to eliminate bias from extreme global noises.

## 🚀 Key Findings
Both models were evaluated using the Silhouette Coefficient and Davies-Bouldin Index (DBI):

| Algorithm | Silhouette Score | DBI Score | Key Insight |
| :--- | :---: | :---: | :--- |
| **K-Means (k=4)** | 0.7181 | 0.4920 | Successfully delineated 4 macro-level submarkets but forced extreme outliers into standard clusters, blurring true market boundaries. |
| **DBSCAN** | **0.8081** | **0.2855** | Superior performance. Isolated 96 extreme outlier properties (median IDR 4.5 billion) as noise and uncovered a hidden entry-level segment in East Balikpapan. |

**Conclusion:** DBSCAN proved to be the more robust analytical tool for mapping complex, rapidly developing urban submarkets because it handles wild price anomalies without distorting the core market segments.
