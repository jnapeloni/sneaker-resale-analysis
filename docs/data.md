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
| `item`                 | Sneaker name                                                                                                 |
| `brand`                | Sneaker brand                                                                                                | 
| `retail`               | Retail price                                                                                                 |
| `release`              | Release date                                                                                                 |
| `lowestAsk`            | Lowest ask price by seller                                                                                   |
| `numberOfAsks`         | Number of asks                                                                                               |
| `salesThisPeriod`      | Number of sales this period (12-month period)                                                                | 
| `highestBid`           | Highest bid by buyer                                                                                         |
| `numberOfBids`         | Number of bids                                                                                               |
| `annualHigh`           | Highest sale price reached on annual basis                                                                   |
| `annualLow`            | Lowest sale price reached on an annual                                                                       |
| `volatility`           | Volatility in sale price (measured in percentage, 12-month period)                                           |
| `deadstockSold`        | Number of total deadstock pairs sold                                                                         |
| `pricePremium`         | Measure of average sale price above retail price (measured in percentage)                                    |
| `AvgDSPrice`           | Average sale price for unused and unworn sneakers                                                            |
| `lastSale`             | Most recent sale price                                                                                       |
| `jordan.type`          | Type of Jordan sneaker (N/A if not a Jordan sneaker)                                                         |
| `collab`               | Collaboration with other brand (0 = No, 1 = Yes)                                                             |

## Data Processing and Cleaning Steps
  1. **Loading the Data**: The dataset was loaded into RMarkdown using:
     ```r
     sneakers <- read.csv("/data/sneakers2023.csv", sep = ",", header = T)
     ```
  2. **Remove First Column**: The first column of the data was removed, as it contained observation numbers which were unnecessary. A new dataframe, named `sneakers.clean`, was created in this process through the following code:
     ```r
     sneakers.clean <- sneakers[,-1]
     ```
  3. **Brand Variable Specification**: The 'brand' variable was replaced for sneakers with more specific brand types for the following:
    - The brand variable 'adidas' was replaced with 'Yeezy' for Adidas sneakers that are of the Yeezy model 
    - The brand variable 'nike' was replaced with 'Nike SB' for Nike sneakers that are apart of the Nike SB line
    - The brand variable 'nike' was replaced with 'Nike Dunk' for Nike sneakers that are of the Nike Dunk model
    - The brand variable 'nike' was replaced with 'Nike AF1' for Nike sneakers that are of the Nike Air Force 1 model
  4. **Adding Jordan Variable**: The `jordan.type` variable was created and added to the dataset to specify the type of Jordan sneaker. Non-Jordan sneakers were filled with N/A values
  5. **Adding Collaboration Variable**: The `collab` variable was created and added to the dataset to indicate whether a sneaker was apart of a collaboration between two sneaker brands, or between a sneaker brand and non-traditional sneaker brand. Values of 0 indicate _no collaboration_ and 1 indicates _apart of a collaboration_
  6. **Handling Incorrect or Missing Values**:
     - Observation 1334 (Jordan 1 Low SE True Blue) had an incorrect retail price, which was adjusted from 1100 to 110, which is the correct value
     - Observations with missing or 0 values were removed from the data, as these were not accurate.
  7. **Formalize `ASICS` Brand Name**: The brand 'ASICS' was not spelled consistently within the data. All ASICS brand sneakers were made to be spelled consistently as 'ASICS' within the `brand` variable.
  8. **Simplifying Variable Name**: The original dataset contained an `averageDeadstockPrice` variable, which was shortened to `AvgDSPrice` for simplicity 
     


