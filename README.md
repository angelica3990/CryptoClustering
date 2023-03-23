
## Instructions

- Get the summary statistics and plot the data to see what the data looks like before proceeding.
![image](https://user-images.githubusercontent.com/62813833/227232658-56934606-25bc-4698-aca1-117100c3f61c.png)


#### Prepare the Data
- Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
![image](https://user-images.githubusercontent.com/62813833/227232851-ca38f0be-4c4b-45b0-aa1d-ec2efa38c836.png)

#### Find the Best Value for k Using the Original Scaled DataFrame
- Use the elbow method to find the best value for k.
![image](https://user-images.githubusercontent.com/62813833/227233136-eeb5ae28-6b8b-497f-86ad-2e5c9d6e82b9.png)
    - 4 is the best value


#### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the original scaled DataFrame.
- Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
- Create a copy of the original data and add a new column with the predicted clusters.
- Create a scatter plot using hvPlot as follows:
- Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
- Color the graph points with the labels found using K-means.
- Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
![image](https://user-images.githubusercontent.com/62813833/227233389-3cfe42a6-ede3-4120-a23f-7322ba7f280f.png)



#### Optimize Clusters with Principal Component Analysis
- Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component.
- Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
![image](https://user-images.githubusercontent.com/62813833/227233899-b13a7888-2350-4055-8554-ce9961b7c43e.png)


#### Find the Best Value for k Using the PCA Data
- Use the elbow method on the PCA data to find the best value for k using the following steps:
    -   Create a list with the number of k-values from 1 to 11.
    -   Create an empty list to store the inertia values.
    -   Create a for loop to compute the inertia with each possible value of k.
    -   Create a dictionary with the data to plot the Elbow curve.

#### Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the PCA data.
- Predict the clusters to group the cryptocurrencies using the PCA data.
- Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
![image](https://user-images.githubusercontent.com/62813833/227234127-7a38ae00-1229-4f46-afef-efe5833bdcb2.png)

