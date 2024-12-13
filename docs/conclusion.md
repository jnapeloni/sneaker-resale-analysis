---
layout: default
title: Conclusions 
--- 

# Conclusions 

## Summary of Findings 

This project aimed to analyze and uncover the key factors that contribute to the variation and increase in sneaker prices on the resale market. Through my analysis, I uncovered several key findings: 

  1. **Brand**:
     - 'Yeezy' brand sneakers are associated with higher prices on the resale market compared to other brands.
     - 'Nike SB' brand sneakers are also associated with higher resale prices. This is likely due to their resurgence in popularity within the sneaker-collector community. 
     - 'Jordan' brand sneakers are associated with higher prices on the resale market. Specifically, Jordan 4 and Jordan 1 models are most associated with higher resale prices.
    
  2. **Collaboration**:
     - Sneakers that are apart of a collaboration are associated with higher prices on the resale market compared to those that are not.

  3. **Key Variables and Clustering**:
     - Through principal component analysis, variables such as the lowest asking price, the average deadstock price, and the most recent sale prices are important in explaining the variation within the data.
     - The collaboration indicator variable, along with retail price, are also important in explaining the variation within the data.
     - The first principal component, including variables such as the lowest asking price and the avergae deadstock price, is most useful in clustering similar sneakers together
    
## Limitations: 

While this analysis was useful in detecting the key features of sneakers are associated with increased and similar resale prices, a few important limitations should be acknowledged. 

  1. **Survivorship Bias**:
     - The dataset contains observations from the first 25 pages of StockX's catalog, meaning that these sneakers were the most popular / most frequently interacted with at the time of scraping.
     - Less popular sneakers, or sneakers with fewer transactions, were not included as a part of this dataset. This may result in bias towards sneakers with higher resale prices, while sneakers with lower resale prices were not included in the dataset.
    
  2. **Unobserved Characteristics**:
     - Some sneakers generally achieve higher resale prices based on unobservable characteristics, such as if they are produced in extremely limited quantities, are apart of highly coveted collaborations (ex. Travis Scott, OFF-WHITE, etc), or carry some nostalgia factor for sneaker collectors (Original colorways or design). These factors are not observed or included within the dataset, although may lead to an increase in resale prices.
    
## Future Work: 

Based on the results of this analysis, along with the consideration of its limitations, there are a few potential avenues for future research: 

  1. **Additional Variable Considerations**:
     - Including more detailed variables, such as collaboration brand or number of pairs produced, may be useful in further analyzing the relationships between sneaker characteristics and their resale prices
    
  2. **Expanded Dataset**:
     - As mentioned in the limitations section, this dataset contained observations from the first 25 pages of StockX's catalog. More extensive analysis can be performed on a larger dataset of sneakers, which contains observations beyond the most popular and frequently interacted with on the resale market.
    
## Final Words: 

This project provides a detailed analysis of sneakers on the resale market. Statistical tools, such as Principal Component Analysis and Clustering Analysis, were implemented to detect key contributing variables of increased resale prices, as well as to detect similar sneakers based on underlying factors. This analysis revealed that both sneaker brand and collaborations with other brands are significantly associated with higher resale prices. 

While these methods were useful in detecting key contributing factors to increased resale prices and detecting similar sneakers, future work can be done to improve this analysis. 

Thank you for checking out this project and analysis! All code and datasets used can be found in the [GitHub Repository](https://github.com/jnapeloni/sneaker-resale-analysis/tree/main)! 
