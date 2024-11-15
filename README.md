# CryptoClustering

###  Introduction

This code is predicting if cryptocurrencies are affected by 24 hours or 7-day changes in prices by using Python and Unsupervised learning.

### Libraries and Dependecies Used
+ pandas
+ hvplot.pandas
+ sklearn.cluster imported KMeans
+ sklearn.decomposition imported PCA
+ sklearn.preprocessing imported StandardScaler

### Data Preparation and Analysis
1.  The data was normalized used the StandardScaler Module of SciKit-Learn.

2.  The best value of `k` was found to be **4** using the _elbow method_.
    - This included iterating through a `for` loop for k values from 1 to 11 to compute the _inertia_.
    - Dictionary was used to store the inertia and k values.
    - Using hvplot module, a line chart was then generated from this dictionary to visualize the optimal k value.

3.  The unsupervised learning problem: **Clustering** was then to predict the data.
    - K-mean model was used with the optimized k value found in step 2.
    - this K-means model was then fitted on the dataset.
    - Clusters were predicted to group the cryptocurrencies.

4.  Using hvPlot, a scatterplot was generated on the 2 columns "price_change_percentage_24h" on the x-axis and "price_change_percentage_7d" on the y-axis with a colour code based on the k-means number.

5.  Cluster predictions was then repeated using Principal Component Analysis (PCA) on three principal components.
    - The explained variance was computed and then the total explained variance was calculated and found to be **89.5%**
    - Steps 2 through 3 was then repeated on the PCA scaled dataset where:
        - Optimal K-Means was still **4**.
        - Clusters were predicted by plotting PCA1 on x-axis and PCA2 on y-axis.


### Analysis

1. The composite plot below compares the two elbow tests performed for the normalized scaled data and the PCA scaled data.

![Screenshot of composite plot comparing the two Elbow Tests.](https://github.com/Zenalawrence/CryptoClustering/blob/main/README_images/Image1_composit_elbow.png?raw=true)

This plot shows optimal K-Means value of 4.  PCA had a lower inertia indicting tighter clusters was predicted.

2.  The total explained variance was found to be 89.5% for 3 principal components features.

3.  The composite plot below shows the two plots for normalized scaled dataset and PCA scaled dataset.

![Screenshot of composite plot comparing the two Elbow Tests.](https://github.com/Zenalawrence/CryptoClustering/blob/main/README_images/image2_composite_scatter1.png?raw=true)

    - The Original scaled data plot shows clustering overlap each other as shown by the green and blue colours (cluster 0 and 3).
    - Using fewer feaures allowed tighter and more distanced clustering for the PCA scaled data.  "Celsius-degree-token" shown in green colour(cluster 0), is nested amongst the blue colour(cluster 0) in the original scaled data compared to the PCA scaled data.  The four clusters is better visualized in the PCA analysis as a result of the few features.

