# Adease_time_series

Project overview and goals : 

The objective of this project is to solve the problem of forecasting future web traffic for approximately 145,000 wikipedia articles in different languages. 

Technical details : 

Each of these time series represent a number of daily views of a different Wikipedia article, starting from July, 1st, 2015 up until December 31st, 2016.

 For each time series, we were provided with the name of the article as well as the type of traffic that this time series represent (all, mobile, desktop, spider)

 We need to optimize for Mean Absolute Percentage Error [MAPE] for diiferent Time series models and present the best model with lowest MAPE.

caution : 

Unfortunately, the data source for this dataset does not distinguish between traffic values of zero and missing values. A missing value may mean the traffic was zero or that the data is not available for that day.





