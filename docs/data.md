---
layout: default  
title: "Data Description" 
---

# Data Description 

## Dataset Overview 

The dataset used in this analysis is the **StockX Sneaker Data** which contains information about sneakers and their sale history. This data comes from scraping the first 25 pages of StockX's (a popular sneaker resale marketplace) catalog in March 2023. The data includes information relating to both sneaker characteristics and resale market data, such as latest sale price, highest bid, lowest ask price, amongst others. 

  - **Source**: This data is available from [Kaggle](https://www.kaggle.com/datasets/ajiaron/stockx-sneaker-data)

## Data Features 

This dataset contains the following variables: 

| Variable Name          | Description                                                                                                  | 
|------------------------|----------------------------------------------------------------------------------------------------------------|
| 'item'                 | Sneaker name                                                                                                 |
| 'brand'                | Sneaker brand                                                                                                | 
| 'retail'               | Retail price                                                                                                 |
| 'release'              | Release date                                                                                                 |
| 'lowestAsk'            | Lowest ask price by seller                                                                                   |
| 'numberOfAsks'         | Number of asks                                                                                               |
| 'salesThisPeriod'      | Number of sales this period (12-month period)                                                                | 
| 'highestBid'           | Highest bid by buyer                                                                                         |
| 'numberOfBids'         | Number of bids                                                                                               |
| 'annualHigh'           | Highest sale price reached on annual basis                                                                   |
| 'annualLow'            | Lowest sale price reached on an annual                                                                       |
| 'volatility'           | Volatility in sale price (measured in percentage, 12-month period)                                           |
| 'deadstockSold'        | Number of total deadstock pairs sold                                                                         |
| 'pricePremium'         | Measure of average sale price above retail price (measured in percentage)                                    |
| 'AvgDSPrice'           | Average sale price for unused and unworn sneakers                                                            |
| 'lastSale'             | Most recent sale price                                                                                       |
| 'jordan.type'          | Type of Jordan sneaker (N/A if not a Jordan sneaker)                                                         |
| 'collab'               | Collaboration with other brand (0 = No, 1 = Yes)                                                             |

## Data Processing and Cleaning 


