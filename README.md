# Adease web traffic time_series forecast

## Project overview and goals : 

The objective of this project is to solve the problem of forecasting future web traffic for approximately 145,000 wikipedia articles in different languages. 

## Technical details : 

Each of these time series represent a number of daily views of a different Wikipedia article, starting from July, 1st, 2015 up until December 31st, 2016.

 For each time series, we were provided with the name of the article as well as the type of traffic that this time series represent (all, mobile, desktop, spider)

 We need to optimize for Mean Absolute Percentage Error [MAPE] for diiferent Time series models and present the best model with lowest MAPE.

caution : 

Data size is huge, breaches 100 MB limit on github free version.

Unfortunately, the data source for this dataset does not distinguish between traffic values of zero and missing values. A missing value may mean the traffic was zero or that the data is not available for that day.

## Why MAPE : 

MAPE importance :

Mean Absolute Percentage Error (MAPE) is a commonly used metric in time series forecasting and other applications where errors are measured as a percentage of the actual values.

MAPE is calculated as the average of the absolute percentage errors between the predicted values and the actual values. It is expressed as a percentage and provides a measure of the average magnitude of the errors relative to the actual values.

Think of MAPE as a measure of how much better or worse the forecast is than the actual values.

# Results :

* Arima - (1,1,1) # no seasonality

MAPE 0.0669088024208379

* Arima - (2,1,2) # no seasonality

MAPE 0.07418494010841041

* SARIMAX(order=(1,1,1),seasonal_order=(1,1,1,7))

MAPE 0.04940946846240072

* Hyper parameter tuned : 

SARIMAX(order =(1, 1, 1),seasonal_order =(2, 1, 1, 7))

MAPE 0.041895

* PROPHET : 

MAPE : 0.04233830598310036

* Simple LR : 

MAPE : 0.044969283321829576	 

we can observe that Hyper-parameterized SARIMAX model gives best MAPE , followed by prophet and  a simple linear regression model.

* Inferences made from the data visualizations:

     * Total 7 languages found in data.

     *  English has the highest number of pages.

     *   3 access types:

         * all-access 51.2295 %
         * mobile-web 24.7748 %
         * desktop 23.9958 %

     * 2 access origins:

         * agents 75.932526 %
         * spider 24.067474 %
         
   * English language has the highest pages.

   * Maximum ads should be run on English Pages.
 
 # Model description : 

 * ARIMA (AutoRegressive Integrated Moving Average) is a statistical model for time series data that accounts for both autoregression (the use of past values to predict future values) and moving average (the use of the residuals of past predictions to predict future values).
* It is a flexible method for modeling non-stationary time series data and can be used for both univariate and multivariate time series.
* ARIMA models are denoted by the notations ARIMA(p, d, q), where p is the order of the autoregression component, d is the order of differencing used to make the time series stationary, and q is the order of the moving average component.

*  SARIMA (Seasonal AutoRegressive Integrated Moving Average) is a variation of ARIMA that accounts for both seasonality and non-stationarity in time series data.
* Seasonality refers to repeating patterns in the data over fixed time intervals, such as daily, weekly, or yearly. SARIMA models are denoted by the notations SARIMA(p, d, q)(P, D, Q, S), where p, d, and q are the same as in ARIMA models, P is the order of the seasonal autoregression component, D is the order of seasonal differencing, Q is the order of the seasonal moving average component, and S is the number of seasons in the data.

* SARIMAX (Seasonal AutoRegressive Integrated Moving Average with exogenous regressors) is an extension of SARIMA that allows for the inclusion of exogenous variables, or variables that are not part of the time series data, in the modeling process.
  SARIMAX models are useful when the time series data is influenced by other variables that are not part of the time series data, and can provide more accurate forecasts.
  SARIMAX models are denoted by the notations SARIMAX(p, d, q)(P, D, Q, S)x, where p, d, q, P, D, Q, and S are the same as in SARIMA models and x represents the number of exogenous variables included in the model.








