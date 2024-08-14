# CryptoClustering

This exercise is meant to show how using k_means and scaling to reduce the resources needed to make market predictions while maintaining data accuracy. 

## Libraries and Dependencies:

pandas

hvplot.pandas

sklearn.cluster (KMeans)

sklearn.decomposition (PCA)

sklearn.preprocessing (StandardScaler)


## Data Cleaning

The data is made up of the price change of cryptocurrencies (as percentages) within various time frames starting from 24 hours to one year. To start, the data was read from a csv and added to a new dataframe. The "coin_id" column listing the cryptocurrency name was set as an index column. Then the data was plotted on a line chart to show what information is within the dataframe. The data was then normalized using the StandardScaler module from scikit-learn and saved as a new dataframe.

## Original K-Model

Using KMeans and a for loop, I calculated inertia and plotted the data in an elbow chart. The k-values tested ranged from 1-11. Once plotted I could determine the best value of 'k' as 4. Using KMeans again but this time specifying 4 clusters, I used scikit-learn prediction to determine the cluster of each cryptocurrency. I was able to create a scatter plot charting the change in price after 24 hours to the price change after 7 days. 

## Principal Component Analysis

To decrease the resources needed to predict these clusters, I created a second model using Principal Component Analysis. Instead of 7 columns of various time frames, I wanted to reduce the features to 3 (PC1-PC3). Using PCA modeling I identified the variance between each component (cryptocurrency) and determined the variance ratio to have a sum of 89.5%. This means that the cumulative explained variance of the new components captures a large portion of the data's variability and will help reduce the dimensions within our original data while maintaining accuracy.

## PCA K-Model

Now that we have reduced the number of dimensions, a new k-model using the PCA data was created in the same fashion as our original. A for loop ranged through values 1-11 and was plotted on an elbow chart to identify the best possible value for 'k'. Just as shown in our original model, 4 was determined to be the optimum value. Having confirmed the correct value for 'k' a scatter plot of the predicted value comparing PC1 (x-axis) and PC2 (y-axis). 

## Summary

Having created the elbow and scatter plots, they were combined into two new charts to help visualize the potential changes in the data from the original scaled market data to the PCA data. The combined charts show very little variability indicating that the PCA data can be used to not only reduce the number of dimensions and features of the original data but also the resources needed to run the model with confidence in the data accuracy. 


