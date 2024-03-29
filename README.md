# Asset Class Hierarchical Clustering

## Description

In this project, I hierarchically cluster major asset classes in the investment landscape, using their correlations to derive a measure of distance. These correlations&mdash;both monthly and quarterly&mdash;are derived using the historical return streams of various ETFs, which serve as proxies for these asset classes; using ETFs as opposed to actual indices allows historical data to be easily retrieved with an open-source API (here, I used Alpha Vantage's). After converting the correlation matrix into a distance matrix, agglomerative clustering is performed by SciPy's ```linkage``` function, which, as opposed to scikit-learn's AgglomerativeClustering class, is natively plottable as a dendrogram. Average linkage is the metric by which distances between clusters are updated as they grow. Ultimately, the results of this work provide a clearer picture of how different asset classes relate to one another; this can in turn lead to better investing, as possessing a range of uncorrelated assets mitigates downside risk and provides additional robustness to an overall investment strategy.

## Dependencies

- NumPy
- Pandas
- SciPy
- Matplotlib
- Seaborn
- Requests (only if fetching updated stock data)

For a full list of dependencies—both direct and transitive—please refer to the provided requirements.txt file.

## Usage

The analysis itself is located at ```/model/Asset-Class-Hierarchical-Clustering.ipynb```. This file walks you through the overall process from beginning to end, from fetching the data using an API to deriving the distance matrix and finally to constructing hierarchical trees and sorted correlation matrices. The underlying historical stock price data can be found at ```/data/total_ticker_prices_df.csv```; with this file, the data-fetching section of the .ipynb file can be skipped.

## Data Sources

Historical stock price data: API from [Alpha Vantage](https://www.alphavantage.co/)