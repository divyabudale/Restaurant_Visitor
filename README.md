Objective : In this project, time-series forecasting problem centered around restaurant visitors was handled. The goal was to predict the total number of visitors to a restaurant for future dates based on reservation and visitation data

Motivation :  I wanted to study the techniques to identify seasonality and trend in a timeseries forecasting and how eliminating both can help in forecasting. 

Data : The data comes from two separate sites:

Hot Pepper Gourmet (hpg): similar to Yelp, here users can search restaurants and also make a reservation online
AirREGI / Restaurant Board (air): similar to Square, a reservation control and cash register system
You must use the reservations, visits, and other information from these sites to forecast future restaurant visitor totals on a given date. The training data covers the dates from 2016 until April 2017. The test set covers the last week of April and May of 2017. The test set is split based on time (the public fold coming first, the private fold following the public) and covers a chosen subset of the air restaurants. Note that the test set intentionally spans a holiday week in Japan called the "Golden Week."

File Descriptions
This is a relational dataset from two systems. Each file is prefaced with the source (either air_ or hpg_) to indicate its origin. Each restaurant has a unique air_store_id and hpg_store_id. Note that not all restaurants are covered by both systems, and that you have been provided data beyond the restaurants for which you must forecast. Latitudes and Longitudes are not exact to discourage de-identification of restaurants.

air_reserve.csv
This file contains reservations made in the air system. Note that the reserve_datetime indicates the time when the reservation was created, whereas the visit_datetime is the time in the future where the visit will occur.

hpg_reserve.csv
This file contains reservations made in the hpg system.

air_store_info.csv
This file contains information about select air restaurants. Column names and contents are self-explanatory.

hpg_store_info.csv
This file contains information about select hpg restaurants. Column names and contents are self-explanatory.

store_id_relation.csv
This file allows you to join select restaurants that have both the air and hpg system.

air_visit_data.csv
This file contains historical visit data for the air restaurants.

date_info.csv
This file gives basic information about the calendar dates in the dataset.

The dataset showed seasonality on days of week. The seasonality was removed by using lags. Features were created by merging different datasets, geographical coordinates were used to create additional features, haversine distance was computed, Kmeans was used to cluster the areas, mean encoding was used to convert the store id

Models : Once the data preprocessing was completed, train and validation set was created each having six month period. Linear regression, Lasso regression, Light GBM, XGBoost, Gradient Boosting, KNeighbours algorith was used to create the forecasting models. Stacking and Blending of different model was also performed. 

Results : Out of the number of models, ultimately, though XGboost resulted in the best performing model with RMSLE of 0.48279


