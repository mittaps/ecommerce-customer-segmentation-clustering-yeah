# E-Commerce User Segmentation: RFM Analysis and K-Means Clustering

## Project Overview
This repository contains a comprehensive data science workflow designed to segment e-commerce users based on their demographic profiles and transactional behaviors. By applying RFM (Recency, Frequency, Monetary) analysis and unsupervised machine learning (K-Means Clustering), this project categorizes the customer base into distinct segments to drive targeted marketing and strategic business decisions. 

**Interactive Dashboard:** [View the Complete Looker Studio Visualization Here](https://datastudio.google.com/u/0/reporting/8f2ec94f-d1e3-454f-92ba-d8295ce90578/page/HXD2D)

## Methodology and Workflow

### 1. Data Preprocessing & Cleansing
* **Data Integration:** Merged primary user demographic data with transaction history.
* **Anomaly Resolution:** Handled severe age outliers (e.g., birth years exceeding 2006 across various regional segments like SC33, SC61, SC62, and SC93) using statistical imputation (mean/median distribution and manual chronological binning).
* **Feature Engineering:** Developed advanced behavioral metrics including:
  * `total_spent` and `total_price`
  * `refund_ratio` and `wallet_balance` adjustments
  * **RFM Metrics:** `rfm_recency`, `rfm_frequency`, and `rfm_monetary_value`.

### 2. Dimensionality Management
* Filtered out negative anomalies in transactional columns (negative money spent, tenure, and total price).
* Dropped redundant date columns post-feature extraction.
* Applied `MinMaxScaler` to normalize highly skewed transactional data, ensuring distance-based algorithms operate accurately. Linear inversions were applied to specific features (`refund`, `rfm_recency`, `discounts`) to align the clustering logic.

### 3. Machine Learning Application
* **Algorithm:** Implemented K-Means clustering utilizing the PyCaret library for rapid model deployment and evaluation.
* **Evaluation:** Analyzed optimal cluster counts using Elbow method visualizations and silhouette scoring.
* **Execution:** Successfully segmented the cleansed dataset into 4 distinct customer clusters (Cluster 0 to Cluster 3), outputting the final assigned dataset for business intelligence consumption.

## Technology Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn, PyCaret
* **Visualization:** Matplotlib, Seaborn, Plotly, Looker Studio
