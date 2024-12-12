---
layout: default
title: "Methodology"
---

# Methodology 

## Data Preprocessing 

Before any statistical analysis, the following steps were taken to prepare the data for analysis: 
  1. **Feature Engineering**:
  - Created `jordan.type` variable to identify the specific model of Jordan sneaker. N/A values were assigned to non-Jordan sneakers 
  - Created `collab` variable to indicate whether sneakers were apart of a collaboration between brands
  2. **Encoding `collab` Variable**:
  - The `collab` variable was converted to numeric to allow for inclusion in principal component analysis. Sneakers apart of collaborations were assigned a '2' and sneakers that are not apart of a collaboration received a '1'
  3. **Subsetting Data**:
  - A subset of the original dataset was created which only included 'Nike' brand shoes. This was done in preparation for exploratory data analysis and was named `sneakers.nikes`
  - A subset of the original dataset was created which only included the most frequently occurring brands in the dataset. These are 'Nike', 'Nike SB', 'Nike Dunk', 'Nike AF1', 'Jordan', 'adidas', 'Yeezy', and 'New Balance'. This was done in preparation for exploratory data analysis and was named `sneakers.brands`
  - A subset of the original dataset was created which only included quantitative variables. These are `retail`, `lowestAsk`, `numberOfAsks`, `salesThisPeriod`, `highestBid`, `numberOfBids`, `annualHigh`, `annualLow`, `volatility`, `deadstockSold`, `pricePremium`, `AvgDSPrice`, `lastSale`, `collab`. This was done in preparation for principal component analysis and was named `sneakers.quant`  

## Exploratory Data Analysis (EDA) 

I conducted exploratory data analysis univariately to view distributions of both quantitative and categorical variables in the data. 

  - **Univariate Analysis**
    - Histograms were created to observe the distributions of six quantitative variables in the data.
      <img src="images/Histograms.png" alt="drawing" width="600"/>
    - Barplots were created to observe the frequency of categorical variables in the data.
      <img src="images/Barplots.png" alt="drawing" width="600"/>

## Statistical Modeling 

Multiple statistical models were applied to identify the most important factors influencing sneaker resale prices, as well as to analyze trends and associations between similar sneakers on the resale market. 

### a. Principal Component Analysis 

  - **Goal**: The goal of PCA is to reduce the dimensionality of the data to observe the variables that best explain trends and patterns within the data.
  - **Implementation**:
    - PCA was implemented on the subset of data containing only the quantitative variables in the data, `sneakers.quant`.
    - The `collab` variable was treated as numeric, which is further explained in the Data Preprocessing section of this project.
    - The data was standardized in implementing PCA to ensure the variables were measured on an equal scale.
    - Principal Component Regression was performed using the first two principal components, in which `AvgDSPrice` was chosen as the dependent variable. 
  - **Results**:
      - A screeplot and cumulative proportion of variance plot were created to determine an appropriate number of principal components. Based on these plots, The first two principal components explain approximately 80% of the variance in the data. Thus, I chose to utilize 2 principal components in this analysis.
      - Barplots containing the loadings for the first two principal components were created in order to determine which variables contribute most to each component. Based on the barplots and loadings, Average DeadStock Price, Last Sale Price, and Lowest Ask Price are loaded high for the first component. The collaboration and retail price variables are loaded high for the second principal components.
      - A biplot plotting the data points with the first two principal components on the axes was created to visualize the loadings and significance of the variables' contributions to each principal component.

### b. K-Means Clustering 

  - **Goal**: The goal of k-means clustering is to partition the data based on the variables using a step-wise approach into non-overlapping groups.
  - **Implementation**:
     - K-means clustering analysis was implemented on a subset of the data containing only quantitative variables, `sneakers.quant`
     - A plot using the CH-Index to measure between-cluster variation was created to determine the optimal number of clusters
  - **Results**:
     - The between-cluster variation plot utilizes the CH-Index to determine the optimal number of centers (or clusters) to use when implementing k-means clustering. Based on this plot, the CH-Index reaches its largest value when utilizing 4 clusters. Thus, I chose to use 4 centers in k-means cluster analysis.
     - K-means clustering utilizing 4 centers was applied to the dataset and plotted with the first two principal components on the axes. Based on the plot, it appears that the first principal component was most influential in determining cluster assignment for this data. 

### c. Hierarchical Clustering 

   - **Goal**: The goal of hierarchical clustering is the cluster the data based on a predetermined linkage function, which specifies the function used to cluster the data. Hierarchical clustering was implemented as an additional form of analysis to further understand the underlying variables 
   - **Implementation**:
       - Hierarchical clustering was implemented using a subset of the data which only contained quantitative variables, `sneakers.quant`
       - The new dataset was scaled to ensure that the data was standardized before use
       - A distance matrix was created from the scaled data using euclidean distance
       - The minimax linkage function in the 'protoclust' R package was applied to the distance matrix for hierarchical clustering analysis
   - **Results**:
       - The minimax linkage function was chosen out of a potential five linkage functions (single, complete, centroid, and average) because it produced the most effective clustering of the data. The data was grouped into 4 clusters based on the minimax linkage function and was then plotted with the first two principal components on the axes. The datapoints were replaced with a number representing each observation's cluster assignment (cluster 1, 2, 3, or 4) and each cluster was plotted in a different color to easily identify the different clusters. The plot suggests that the first principal component is important in explaining and clustering the data, as it creates four distinct clusters which are separate from one another.


Further results, analysis, and interpretations can be found in the [Results](results.md) section
      
