# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Ames Housing Data and Kaggle Challenge


### Background

The city of Ames is located in the Iowa State of U.S.

The property market housing in Ames is stable, consistently selling around 400 units per year from 2006 to 2009 despite the fact that US experienced the Subprime financial crisis during that period. As of July 2010, the number of properties sold ranges around 200 units, on track to meeting the calculated average of around 400 units sold per year.

Amongst the many Property Advisors in Ames is the Skywalker Property Advisors.

As data scientists contracted by Skywalker Property Advisors, the 5am Club Data Science Agency has been tasked with analysing the data of properties sold between 2006 to 2010 (up till July). The analysis and observations gathered will be used to give recommendations and advices to the realtors of Skywalker Property Advisors to help improve their sales and gain a competitive advantage in the Ames Housing Market in the current year of 2010.


### Problem Statement

This project aims to identify areas contributing to high transacted prices and where the highest transacted volume occurs, using a data science approach, so as to help realtors of Skywalker Property Advisors gain a competitive advantage in the Ames Housing Market.


### Data Dictionary
Refer to the Jupyter notebook of "Data_Dictionary.ipynb" in the Codes folder


### Analysis Summary

The Ridge Model was chosen with the following results obtained:

|Model |Mean Train CV R^2|Mean Test CV R^2|Test Set RMSE|
|:---:|:---:|:---:|:---:|
|**Baseline**|0|0|79 239 (for all models)|
|**Ridge Model**|0.840|0.879|25 973|

Using the Ridge Model, the top 10 features with Positive coefficient and top 10 features with Negative coefficient was generated, which affects the sale price of housing in a positive and negative mannger respectively.

The following are points that **positively impacts** the sale prices:

1. **Neighborhood**
*Observations*: 
2 neighborhoods with positive impact on saleprice (Northridge Height and Northridge) and 3 neighborhoods with negative impact on saleprice (Edwards, North Ames and Old Town).

Houses in Northridge Heights and Northridge have mean sale price of >$300,000, yielding higher amount of revenue and commission.

Houses in North Ames, Edwards, and Old Town have mean sale price of <$150,000, yielding lesser amount of revenue and commission.

*Recommendation*:
Realtors could focus more on marketing the houses in Northridge Heights and Northridge to generate higher revenue through higher sale prices.

2. **Quality of House**
*Observations*: 
The Overall, Exterior and Kitchen Qualities of the house have a positive impacts on sale prices. Higher quality values for these 3 features show higher house mean sale price.

*Recommendation*:
- Clients with below average housing quality, can be advised to refurbish their home to improve house sale price
- Clients with average/good housing quality, can be persuaded to further improve housing quality to differentiate themselves from the rest of the market and increase their sale price

3. **Fireplaces**
*Observations*: 
Houses with more fireplaces have higher sale prices. Particularly large jump in sale price for houses with no fireplaces compared to houses with 1 fireplace.

*Recommendation*:
Advise clients to build a fireplace if they do not have one in order to increase the sale price of their house

4. **Square Footage of House**
*Observations*: 
Square footages of houses, namely, 1st floor, 2nd floor and garage areas, positively impacts the sale price of houses.
Houses that are most commonly sold have 1st floor square footage of 800-900 sqft, 2nd floor square footage of 500-900 sqft and garage area of 500 sqft.


The following are points that **negatively impact** the sale prices:

1. **House Exteriors**
*Observations*:
- Hardboard Exteriors
    * Poor moisture resisting properties, prone to rot and mold
    * Requires periodic inspection and maintenance
- Stucco Exteriors
    * Wooden frame underneath
    * Does not do well in wet climates, prone to rot and mold


The following are points that have **negligible impact** on sale prices:
1. **Lot Shape**
2. **Fence**


### Conclusions/Recommendations

To maximise the revenue and give realtors of Skywalker Property Advisors a competitive advantage in the Ames Housing Market, the following points are recommended and should be taken into consideration:
- Focus on marketing the houses in Northridge Heights and Northridge as they have the highest mean sale price
- Advise clients with below average housing quality to refurbish their home, so as to improve their house sale price
- Focus on marketing houses with at least 1 fireplace and encourage clients to build a fireplace if they do not have one as houses with fireplaces have higher sale prices
- Avoid houses with hardboard or stucco exteriors as they are prone to rot and mold ([*Hardboard*](https://www.ehow.co.uk/about_6460464_hardboard-information.html), [*Stucco*](https://homesteady.com/how-6725893-paint-synthetic-stucco.html)) especially with the above average snowfall in Ames ([*Ames Weather*](https://www.bestplaces.net/climate/city/iowa/ames))
- A bigger house may have a higher potential sale price, but that also means that it could have a lower chance of being sold due to a lower number of potential buyers who can afford it


Further improvements to the model and project includes:
- collect data on total number of houses in each neighborhood 
    - this would allow us to evaluate the percentage of houses sold across all neighborhoods
- collect data on demographic of neighborhood and buyers
    - examples include age range, marital status, family size, number of kids
- collect sale price in real value to take into account inflation
    - rate of inflation to allow us to better evaluate past sale prices based on today's economy
- further cleaning of the current datasets to remove outliers and improve model fitting
- try out other regression models