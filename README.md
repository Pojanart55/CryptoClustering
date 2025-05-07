# Cryptocurrency Clustering Analysis

## Overview

This project utilizes unsupervised learning techniques, specifically K-means clustering and Principal Component Analysis (PCA), to analyze and group cryptocurrencies based on their market data, particularly focusing on 24-hour and 7-day price changes. The goal is to identify potential patterns and relationships between different cryptocurrencies based on these volatility metrics and to assess the impact of dimensionality reduction on the clustering results.

## Files

* `Crypto_Clustering.ipynb`: The main Jupyter Notebook containing the Python code for the analysis.
* `Resources/crypto_market_data.csv`: The dataset containing cryptocurrency market information used in the analysis.
* `README.md`: This file, providing an overview of the project, results, and conclusion.

## Libraries Used

* pandas
* hvplot.pandas
* sklearn.cluster (KMeans)
* sklearn.decomposition (PCA)
* sklearn.preprocessing (StandardScaler)
* holoviews
* bokeh

## Workflow

1.  **Data Loading and Exploration:** The `crypto_market_data.csv` file is loaded, and initial data exploration is performed.
2.  **Data Preparation:** Numerical features are scaled using `StandardScaler`.
3.  **Finding the Optimal Number of Clusters (k):** The elbow method suggests an optimal $k$ of 4 for the original scaled data.
4.  **Clustering with Original Scaled Data:** K-means with $k=4$ is applied, and clusters are visualized.
5.  **Dimensionality Reduction with PCA:** PCA reduces the data to three principal components, retaining approximately 89.5% of the total variance.
6.  **Finding the Optimal Number of Clusters (k) with PCA Data:** The elbow method on PCA data also indicates an optimal $k$ of 4.
7.  **Clustering with PCA Data:** K-means with $k=4$ is applied to the PCA data, and clusters are visualized in the PC1-PC2 space.
8.  **Visualization and Comparison:** Composite plots compare the elbow curves and the cluster scatter plots from both the original and PCA-transformed data.

## Results and Conclusion

The analysis revealed that the optimal number of clusters ($k=4$) remained consistent whether using the original scaled data or the PCA-transformed data. However, the visual representation of the clusters differed:

* Clusters generated from the PCA data appeared more distinct and compact compared to those from the original scaled data. This suggests that PCA effectively focused on the directions of maximum variance, potentially leading to better-defined groupings by filtering out less informative noise.
* The composite plots of the elbow curves showed similar trends in inertia reduction as $k$ increased for both datasets, reinforcing the consistency in the optimal $k$.
* Visual comparison of the cluster scatter plots indicated that while the overall number of groups remained the same, the relationships and proximities of individual cryptocurrencies within the clusters were influenced by the dimensionality reduction.

**Conclusion:** Using PCA for dimensionality reduction prior to K-means clustering in this cryptocurrency market data analysis appears to be beneficial. It simplifies the data representation, potentially enhances the separation between clusters, and facilitates visualization without altering the underlying optimal number of clusters. By focusing on the principal components that capture the majority of the variance, PCA can help identify more robust and interpretable groupings of cryptocurrencies based on their price change behavior.

### Acknowledgement
* Using google and https://scikit-learn.org for additional research and code debugging.
