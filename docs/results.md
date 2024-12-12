---
layout: default
title: Results
--- 

# Results 


## 1. Principal Component Analysis Results 

Principal Component Analysis was used to reduce the dimensionality of the data to analyze key variables that explain trends and patterns within the data. 

### a. Screeplot and Cumulative Proportion of Variance plot  

A screeplot and cumulative proportion of variance plot were created to determine an appropriate number of principal components. Based on these plots, The first two principal components explain approximately 80% of the variance in the data. Thus, I chose to utilize 2 principal components in this analysis.
        <p float="left">
          <img src="images/Screeplot_PCA.png" width="400" />
          <img src="images/CumulativePropVar.png" width="400" />
        </p>

### b. Loadings for 2 Principal Components  

Barplots containing the loadings for the first two principal components were created in order to determine which variables contribute most to each component. 

  <img src="images/BarPlots_PCA.png" alt="drawing" width="600"/>

The first barplot displays the loadings for the first principal component, which shows Average DeadStock Price, Last Sale Price, and Lowest Ask Price are loaded high for PC1. The second barplot displays the loadings for the second principal component, which shows that Collaboration and Retail Price are loaded high for PC2. 
        
### c. Biplot for Two Principal Components  

A biplot plotting the data points with the first two principal components on the axes was created to further visualize the loadings and contributions of each variable to the first two principal components.  

  <img src="images/Biplot.png" alt="drawing" width="600"/> 

The biplot further shows that `AvgDSPrice`, `lastSale` and `lowestAsk` are loaded high for the first principal component. It is also important to recognize the cluster of variables loaded similarly for the first principal component, which includes variables such as `annualHigh` and `highestBid`. Thus, this indicates that these variables, while not as important in contribution to the first principal component, may be highly correlated with each other. The biplot further shows that the `collab` and `retail` variables are loaded high for the second principal component. It is important to notice the difference in direction that these variables are loaded, where `collab` is loaded highly negatively and `retail` is loaded positively. This suggests that these two variables, while both contributing greatly to the second principal component, are likely not correlated with each other. 

### d. Correlation Matrix 

Based on the potential associations between the variables shown in the biplot, a correlation matrix was created to further analyze the possible correlations between the quantitative variables in the data. 

   <img src="images/Corr_Matrix.png" alt="drawing" width="600"/> 

In the correlation matrix, a stronger shade of blue represents a stronger, positive, correlation between variables, and lighter shades represent weaker (but still positive) correlations. The lightest shades of blue (almost white) represent a correlation of 0 between variables, or no association. Analyzing the potential relationships between variables, as indicated in the biplot, reveals a strong correlation between the `annualHigh` variable and both the `highestBid` and `AvgDSPrice` variables. Furthermore, there is a strong correlation between the `annualLow` variable and both the `lowestAsk` and `AvgDSPrice` variables. `lastSale` is highly correlated with the `lowestAsk` and `AvgDSPrice` variables. All of these correlations, with some stronger than others, are positive associations. Lastly, the correlation matrix reveals that the `collab` and `retail` variables have a correlation coefficient equal to zero, or that there is no correlation between these variables. 

## 2. Principal Component Regression 

Using the results obtained by applying Principal Component Analysis on the quantitative variables in the data, Principal Component Regression was implemented to determine and quantify the effects of each principal component on a dependent variable, being the `AvgDSPrice` variable. 

   <img 



   



