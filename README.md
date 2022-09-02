# Cryptocurrencies
![crypto](https://github.com/heartgears/Cryptocurrencies/blob/main/Images/Cryptocurrencies.png)

## Summary
Creating an unsupervised machine learning model to predict, process, and cluster data, as well as reduce dimensions, and reduce the principal components using PCA. Various cryptocurrencies are grouped together using K Clusters.

## Technology and Libraries
This analysis was performed entirely using Python and the following imported libraries: 
* Pandas
* Numpy
* Hvplot.pandas
* Plotly.express
* SKLearn (StandardScaler, MinMaxScaler, KMeans, PCA)

## Results
### 1. Data Processing
The following was done to process the data for analysis:

* Removal of cryptocurrencies not being traded.
* Removal of cryptocurrencies without a working algorithm
* Dropping the IsTrading column
* Dropping null values
* Filtering dataset with only mined coins.
* Creating a new DataFrame CoinNames, and using the index from the previous dataset as the index for this new DataFrame, cc_names_df

### 2. Principal Component Analysis
The next steps involved applying PCA to reduce the dimensions to 3 principal components.

The analysis from pcs_df includes columns PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.

### 3. K-means
The K-means algorithm was used to cluster the cryptocurrencies using the PCA data:
* An elbow curve was created using hvPlot to find the best value for K
* Predictions were made on the K clusters of the cryptocurrencies’ data
* A new DataFrame was created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

### 4. Visualization 
The clusters were then plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover:

* A table with tradable cryptocurrencies was created using the hvplot.table() function
* The total number of tradable cryptocurrencies was then printed
* A DataFrame was created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
* A hvplot scatter plot was created where the X-axis was "TotalCoinsMined", the Y-axis was "TotalCoinSupply", the data was ordered by "Class", and it shows the CoinName when you hover over the data point.

![plotly](https://github.com/heartgears/Cryptocurrencies/blob/main/Images/plotly.png)
