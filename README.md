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

## Technology and Tools 
1. Data Transformation - Pandas
2. Database - PostgreSQL
3. Models - SciKit Learn
4. Model Visuals - Matplotlib/Seaborn
5. Dashboard - Tableau Desktop & Public


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


<b>Data Transformation</b>br>
* [Historical Rates 2017-2021](https://github.com/kman4/AirbnbPredictions/blob/main/Data/Transformation/Data%20Transformation%20-%202017-2021%20Calendar%20Rates.ipynb)<br>
* [Calendar Rates - Monthly & Weekly](https://github.com/kman4/AirbnbPredictions/blob/main/Data/Transformation/Data%20Transformation%20-%202017-2021%20Calendar%20Rates.ipynb)<br>
* [FB Prophet DB - Overall](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Prophet/FB%20Prophet%20Overall/Data%20Transformation/Data%20Transformation%20-%20Prophet%20Overall.ipynb)
* [FB Prophet DB - Borough & Neighbourhood](https://github.com/kman4/AirbnbPredictions/blob/main/Data/Transformation/Data%20Transformation%20-%20Prophet%20Borough%20%26%20Neighbourhood.ipynb)


<b>Models</b><br>

* [Random Forest, LGBM, and KNN Regressors](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Regressor/RF_LGBM_KNN_Models.ipynb)<br>
* [Facebook Prophet Trends & Seasonality](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Prophet/FB%20Prophet%20Overall/Prophet_Overall.ipynb)<br>
* [Facebook Prophet Predictor by Borough & Room Type](https://github.com/kman4/AirbnbPredictions/blob/main/Model/Prophet/FB%20Prophet%20-%20Borough%20%26%20Room%20Type/Prophet_Borough%20%26%20Room%20Type.ipynb)

## Dashboard
[Tableau Dashboard Link](https://public.tableau.com/profile/kapil.pundhir#!/vizhome/AirBnb_Dashboard/AirBnbAnalysis?publish=yes)

## Model Analysis

**Price Correlation - Accommodations and Amenities**

![Image](https://github.com/kman4/AirbnbPredictions/blob/main/Images/Regressor/price_correlation.png)

The correlation heatmap shows that accommodation features have more impact on price than amenities.  This implies that people feel room size, number of bedrooms and bathrooms are more important features to look at when booking an Airbnb.  Amenities features have a lower correlation meaning that they are nice items to have but it is not a basic requirement to have in an Airbnb.

**Features Importance**

<p float="left">
  <img src="https://github.com/kman4/AirbnbPredictions/blob/main/Images/Regressor/rf_feature_importance.png" width="400">
  <img src="https://github.com/kman4/AirbnbPredictions/blob/main/Images/Regressor/lgbm_feature_importance.png" width="400"> 
</p>

Both models show that the most important features that impact the listings price include Room Type, Neighbourhood and Bathroorms.  Along with accomodations, having your listings in a reputable neighbourhood do have a positive impact on price.

**Nearest Neighbours**


![Image](https://github.com/kman4/AirbnbPredictions/blob/main/Images/Regressor/knn.png)

Since we saw that neighbourhood being an important feature from the Random Forest and LGBM Regressor model, we wanted to see how effective it is to price an Airbnb depending on what your neighbours charge.  As per the graph above, the training and testing scores are quite low.  This maybe due to the fact that there are different room types within the same area.  For example, a hotel room and a shared room can be listed on the same street where the price difference can be at least $200.


**Trends and Seasonality**
![Image](https://github.com/kman4/AirbnbPredictions/blob/main/Images/FB%20Prophet/Price_Predict_Overall.png)

Overall trends show that:
* There are high and low seasons during different times of the year. 
* Upper/lower limits increase overtime as there is more uncertainty in the future.
* With the upward price trend, you can see that Airbnb popularity is on the rise.
* Then in 2020, prices starts decreasing possibly because people travel less during Covid-19.
* From 2022, it shows a slight upward trend as things may improve after the pandemic and people feel safe to travel again.<br>

**Time Components**
![Image](https://github.com/kman4/AirbnbPredictions/blob/main/Images/FB%20Prophet/Price_Predict_Components.png)

The prophet model outputs different time components by holiday, day of week and month.  
* On the holiday chart, it shows Christmas, New Years and long weekends have the highest impact on rates as people then do go on vacations with more days off from work.
* With that being said, the weekly chart indicates the highest rates fall on Fri and Saturday.
* Finally, it shows that the rates do change during different times of the year.  Summer rates are predominantly higher because of better weather and having summer holidays from school.

## Results

* The model predicted that there will be a slight upward trend starting from 2022.
* The centrally located like Manhattan and Brooklyn will have one of the higher rates because it is close to the transit system, main attractions, and the business centers.  
* Hosts should compare their neighbouring listings based on size instead of just taking the whole average because a hotel room vs a private room can have a huge price range.  
* Also offering different prices during holidays, summer, and long weekends can help the host make the most out of their Airbnb income.  
* Having more bathrooms and bedrooms will incrase the price.  
* Offering more amenities like a washer, heat and A/c provides only have a little impact to pricing. 
* Even though the probability is low, but events like the pandemic & 911 will have a major impact on the whole economy and the demand to travel will decrease.


## Team Members

**Amaris Hassan** - Data Research Specialist and Presenter<br>
**Caitlan Beachey** - Tableau Specialist <br>
**Cecilia Leung** - Model Developer and Presenter <br>
**Hillary Mandich** - Project Coordinator <br>
**Kapil Pundhir** - Tableau Specialist & Web Quality Assurance


