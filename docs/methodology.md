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
  - **Results**:
      - A screeplot and cumulative proportion of variance plot were created to determine an appropriate number of principal components. Based on these plots, utilizing 2 principal components appeared significant in explaining approximately 80% of the variance in the data.  
        <img src="images/Screeplot_PCA.png" alt="drawing" width="600"/>





      
