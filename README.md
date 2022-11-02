# ftb10_Unsupervised_Learning


# Module 10 - Crypto Clustering  
In this Challenge, you’ll assume the role of an advisor at one of the top five financial advisory firms in the world. Competitors are fierce, so you want to propose a novel approach to assembling investment portfolios that are based on cryptocurrencies. Instead of basing your proposal on only returns and volatility, you want to include other factors that might impact the crypto market—leading to better performance for your portfolio.

When you present the idea, your manager loves it! So, you’re asked to create a prototype for submitting your crypto portfolio proposal to the company board of directors.

## Repo Layout
    * Instructions - Project detais provided by program
    * Code - New code created to solve the problem
    * Data - csv data files
    * Images - imigaes used in markdown text

## Project Steps
### 1. Import the Data  
      * Read the “crypto_market_data.csv” file from the Resources folder into a DataFrame, and use index_col="coin_id" to set the cryptocurrency name as the index. Review the DataFrame.
      * Generate the summary statistics, and use HvPlot to visualize your data to observe what your DataFrame contains.
      * Data consists of percent cahnge for 41 crypto currencies over 7 time periods (1, 7, 14, 60, 200, and 365 days)
  
### 2. Prepare the Data (provided in the starter code)  
      * Use the StandardScaler module from scikit-learn to normalize the CSV file data. 
        * This will require you to utilize the fit_transform function.
      * Create a DataFrame that contains the scaled data. 
        * Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. 
        * Review the resulting DataFrame.
  
### 3. Find the Best Value for k Using the Original Data  
      * In this section, you will use the elbow method to find the best value for k.
        * Code the elbow method algorithm to find the best value for k. Use a range from 1 to 11.
        * Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
      * Answer the following question: What is the best value for k?

### 4. Cluster Cryptocurrencies with K-means Using the Original Data  
      * In this section, you will use the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the price changes of cryptocurrencies provided.
        * Initialize the K-Means model with four clusters using the best value for k.
        * Fit the K-Means model using the original data.
        * Predict the clusters to group the cryptocurrencies using the original data. View the resulting array of cluster values.
        * Create a copy of the original data and add a new column with the predicted clusters.
        * Create a scatter plot using hvPlot by 
          * Setting x="price_change_percentage_24h" and y="price_change_percentage_7d". 
          * Color the graph points with the labels found using K-Means 
          * Add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### 5. Optimize Clusters with Principal Component Analysis  
      * In this section, you will perform a principal component analysis (PCA) and reduce the features to three principal components.
        * Create a PCA model instance and set n_components=3.
        * Use the PCA model to reduce to three principal components. View the first five rows of the DataFrame.
        * Retrieve the explained variance to determine how much information can be attributed to each principal component.
        * Answer the following question: What is the total explained variance of the three principal components?
        * Create a new DataFrame with the PCA data. 
            * Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

### 6. Find the Best Value for k Using the PCA Data  
      * In this section, you will use the elbow method to find the best value for k using the PCA data.
        * Code the elbow method algorithm and use the PCA data to find the best value for k. Use a range from 1 to 11.
        * Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
      * Answer the following questions: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

### 7. Cluster the Cryptocurrencies with K-means Using the PCA Data  
      * In this section, you will use the PCA data and the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the principal components.
        * Initialize the K-Means model with four clusters using the best value for k.
        * Fit the K-Means model using the PCA data.
        * Predict the clusters to group the cryptocurrencies using the PCA data. View the resulting array of cluster values.
        * Add a new column to the DataFrame with the PCA data to store the predicted clusters.
        * Create a scatter plot using hvPlot by 
            * Setting x="PC1" and y="PC2". 
            * Color the graph points with the labels found using K-Means 
            * Add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### 8. Visualize and Compare the Results  
      * In this section, you will visually analyze the cluster analysis results by contrasting the outcome with and without using the optimization techniques.
        * Create a composite plot using hvPlot and the plus (+) operator to contrast the Elbow Curve that you created to find the best value for k with the original and the PCA data.
        * Create a composite plot using hvPlot and the plus (+) operator to contrast the cryptocurrencies clusters using the original and the PCA data.
        * Answer the following question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?
  
