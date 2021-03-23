# Airbnb Price Predictions

![Image](https://vastphotos.com/files/uploads/photos/10318/high-resolution-new-york-skyline-sunset-l.jpg)

## Background

For this project, we have continued to explore further in New York City's Airbnb pricing.  To ensure that Airbnb listings are fairly priced for both the hosts and the visitors. We hope to do this by the increasing transparency of the process to discover which features of a listing are most correlated with price.  New and existing datasets were cleaned and transformed to conduct our pricing analysis.  Different regression models like Random Forest, Light Gradient Boosting Machine (LGBM), K-Nearest Neighbour (KNN) and Facebook (FB) Prophet were used in Google Colab to determine how seasonality, clustering and features impact the listings prices.  Based on the model results, an interactive dashboard on Tableau has been created for users to give an accurate estimate on their listing based on location, time, and size. 


## Questions

1.	Is location the most important factor in determining listing prices?
2.	How much does the amenities and the size of the unit impact the listing prices?
3.	How does the number of units available within a specific area affect the price of Airbnb?
4.	Do good reviews drive up the rates?
5.	Should a host price their listing differently during a specific time of the week, month, year and holidays?

## Datasets
Get the Data - Inside Airbnb - [http://insideairbnb.com/get-the-data.html](http://insideairbnb.com/get-the-data.html)<br>
US Holidays - [https://www.timeanddate.com/holidays/us/](https://www.timeanddate.com/holidays/us/), [https://www.kaggle.com/benjaminhendler/usholidays](https://www.kaggle.com/benjaminhendler/usholidays)

## Requirements

* Obtain historical rates and holiday dates from the Inside Airbnb and US Holidays website.
* Using the historical rates, create dataframes for monthly and day of week rates in Pandas.
* Load the new tables to the existing PostgreSQL database.
* Impute, encode and vectorize listings dataset to run RF, LGBM & KNN models.
* Create a price correlation matrix, features importance and neighbourhood scores for further analysis.
* Transform dataset with the dates, features and price to run the Prophet model.
* Create a trend and seasonlity graphs for the prices.
* Create a dataset for the predicted and actual prices.
* Upload the actual-predicted dataset to PostgreSQL.
* Connect Database to Tableau.
* Create interactive dashboards.
* Publish dashboards on Tableau public.


## Scripts
[Random Forest, LGBM, and KNN Regressors](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Regressor/RF_LGBM_KNN_Models.ipynb)
[Facebook Prophet Trends & Seasonality](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Prophet/FB%20Prophet%20Overall/Prophet_Overall.ipynb)
[Facebook Prophet Predictor by Borough & Room Type](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Prophet/FB%20Prophet%20-%20Borough%20%26%20Room%20Type/Prophet_Borough%20%26%20Room%20Type.ipynb)

## Model Analysis

## Results

## Dashboard

## Team Members

**Amaris Hassan** - Data Research Specialist and Presenter<br>
**Caitlan Beachey** - Tableau Specialist <br>
**Cecilia Leung** - Model Developer and Presenter <br>
**Hillary Mandich** - Project Coordinator <br>
**Kapil Kundhir** - Tableau & Web Quality Assurance


