# Customer Segmentation System
## Project Purpose

This project helps businesses turn raw transaction logs into actionable customer segments. By computing Recency, Frequency and Monetary (RFM) metrics and applying clustering (K-Means), it identifies distinct customer groups so teams can target retention, loyalty, and marketing strategies more effectively.

## Problem Statement

Retailers often have large volumes of transactional data but lack a simple, repeatable way to group customers by value and behaviour. Manual segmentation is slow and inconsistent. This project automates segmentation to answer questions like:

Which customers are most valuable?

Who are at-risk or inactive customers?

Where should marketing budget be focused to maximize ROI?

## What this project delivers

-> Clean, reproducible pipeline that converts raw invoices into RFM metrics (recency, frequency, monetary).

-> Outlier detection and removal to improve cluster quality.

-> Feature scaling and K-Means clustering with elbow & silhouette analysis to pick the best k.

-> Visualizations (boxplots, elbow curve, silhouette score, cluster profiles) to interpret segments.

-> A simple, interpretable output: cluster labels with average RFM scores for each segment.

## Tech Stack

Python

pandas, NumPy

scikit-learn (KMeans, PCA, silhouette_score, StandardScaler)

SciPy (zscore)

Matplotlib, Seaborn

Jupyter Notebook

## How it works (summary)

-> Load data — read transactional CSV (e.g., data.csv) with invoice, quantity, price, date and customer id.

-> Preprocess — parse dates, compute first/last purchases, and derive recency (days since reference), frequency (orders per customer), and monetary (total spend).

-> Outlier removal — apply z-score filtering to remove extreme RFM values.

-> Scale features — standardize RFM features for clustering.

-> Find optimal k — use the elbow method (inertia) and silhouette score to choose cluster count.

-> Cluster — run K-Means and assign cluster labels.

-> Interpret — compute cluster centroids and plot average recency/frequency/monetary per cluster to name/interpret segments (e.g., Champions, At-Risk, Casual).

## Typical business use cases

-> Targeted email campaigns for high-value customers.

-> Win-back programs for at-risk segments.

-> Personalized promotions and loyalty offers.

-> Resource allocation for retention vs. acquisition.

## Next steps & improvements

-> Use transactional timestamps to compute true recency from a fixed reference date.

-> Experiment with hierarchical or density-based clustering (DBSCAN) for different segment shapes.

-> Add feature engineering: average order value, days between purchases, product affinity.

-> Use PCA or t-SNE for richer visualization of segment separation.

-> Build an automated pipeline (Airflow/Cloud function) to refresh segments periodically.
