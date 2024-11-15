# CryptoClustering
# CryptoClustering

This project uses unsupervised learning techniques in Python to analyze and cluster cryptocurrencies based on their price changes over 24 hours and 7 days. The goal is to determine if cryptocurrencies can be effectively grouped and to analyze if their clusters are influenced by short-term (24-hour) and longer-term (7-day) price changes.

## Table of Contents
- [Overview of Data](#overview-of-data)
- [Project Instructions](#project-instructions)
- [Files](#files)
- [Setup Instructions](#setup-instructions)
- [Analysis Workflow](#analysis-workflow)
- [Results and Insights](#results-and-insights)
- [Technologies Used](#technologies-used)

## Overview of Data

The dataset `crypto_market_data.csv` contains information on various cryptocurrencies, including identifiers, 24-hour price changes, and 7-day price changes. Key fields include:
- `coin_id`: A unique identifier for each cryptocurrency
- `price_change_percentage_24h`: The percentage price change over the last 24 hours
- `price_change_percentage_7d`: The percentage price change over the last 7 days

This data provides insight into both short- and longer-term trends in cryptocurrency markets, which are essential for unsupervised clustering.

## Project Instructions

1. **Repository Setup**:
   - Create a new GitHub repository named `CryptoClustering`.
   - Clone the repository to your local machine, and push all changes to GitHub.

2. **File Setup**:
   - Rename the provided starter file `Crypto_Clustering_starter_code.ipynb` to `Crypto_Clustering.ipynb`.
   - Load the `crypto_market_data.csv` file into a DataFrame and explore its summary statistics and initial visualizations.

3. **Data Preparation**:
   - Use `StandardScaler()` from `scikit-learn` to normalize the data.
   - Create a new DataFrame with scaled data and set the `coin_id` column as the index.

4. **Clustering with K-Means**:
   - **Find the Best Value for k**: Use the elbow method to identify the optimal value of `k` by plotting inertia values across values from 1 to 11.
   - **Cluster Cryptocurrencies**: Using the optimal `k`, apply K-Means clustering and create a scatter plot to visualize clusters based on 24-hour and 7-day price changes.

5. **Optimize Clusters with PCA**:
   - Reduce features to three principal components using Principal Component Analysis (PCA) and calculate the explained variance.
   - Determine the optimal value of `k` for the PCA-transformed data and compare it with the original.

6. **Final Visualization**:
   - Apply K-means clustering on the PCA data and generate a scatter plot of clusters using PC1 and PC2.

## Files

- `crypto_market_data.csv`: The primary dataset containing cryptocurrency price changes.
- `Crypto_Clustering.ipynb`: The Jupyter notebook for conducting the analysis.

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   ```
2. **Install Required Libraries**:
   Install the necessary Python libraries using:
   ```bash
   pip install pandas scikit-learn hvplot
   ```
3. **Load the Notebook**:
   Open `Crypto_Clustering.ipynb` in Jupyter Notebook or JupyterLab to begin the analysis.

## Analysis Workflow

1. **Data Exploration**: 
   - Review summary statistics and initial plots to understand data distributions.

2. **Normalization**:
   - Scale the data to standardize features and remove biases.

3. **Elbow Method**:
   - Plot inertia values for `k` values from 1 to 11 to determine the optimal `k`.

4. **K-Means Clustering**:
   - Cluster the cryptocurrencies based on 24-hour and 7-day price changes.
   - Visualize clusters with a scatter plot and analyze trends.

5. **PCA and K-Means**:
   - Reduce data to three components using PCA, determine the optimal `k`, and re-cluster.
   - Compare results between the original and PCA-transformed data to assess the impact of dimensionality reduction.

## Results and Insights

- **Optimal Clusters**: The elbow method determines the optimal number of clusters (`k`) for both the original and PCA-transformed datasets.
- **Cluster Comparisons**: By comparing clustering with and without PCA, we assess how dimensionality reduction impacts the clustering quality.
- **Explained Variance**: The three PCA components provide insight into the variance captured by each component, helping determine if fewer features adequately represent the data.

## Technologies Used

- **Python**: Programming language for data processing and analysis.
- **Pandas**: Data manipulation and analysis library.
- **scikit-learn**: Machine learning library for scaling, clustering, and PCA.
- **hvPlot**: Visualization library for creating interactive plots.

