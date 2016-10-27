# restaurant

These jupyter notebooks are a preliminary look at how to predict restaurant sales with a transactional dataset. The dataset itself is not currently posted here, but may be in the near future.

## The Dataset

As mentioned, the dataset is a collection of customer transactions at a restaurant. Each customer is described by a number of numerical and categorical variables. Also included is the total spent by the customer.

## Sales Forecast

There are 2 notebooks that cover forecasting. They each demonstrate a different approaches to forecasting. 

1. **The Average Only notebook** uses a basic daily average: Monday we expect the average of all past Mondays, Tuesday we expect the average of all past Tuesdays, etc. This approach was included for 2 reasons:
 1. The dataset does not cover a very large range of dates.
 2. The data exhibits periodicity. 
     
 Therefore, this approach can be considered valid up to this point in the data collection process. In the future, this may not be valid, therefore, another approach was included.

2. **The ARIMA notebook** demonstrates an autogressive approach (ARIMA). While moving averages and seasonality will not manifest (again, due to the range of dates covered by this dataset), this model was found to give good results when 3 autoregressive terms and 2 moving average terms were used to build the model.

Next steps: other options to be explored include:

 - k-fold cross-validation (for a time series, these would be need to be chronologically oriented folds, as it is necessary to preserve the order, and the current lack of data present is not conducive to this approach)
 - other models, such as LSTM (a recurrent neural network)
 
## Modeling Customer Transactions: predicting what a customer will spend

The remaining **"modeling transactions" notebook** demonstrates an approach to predicting what a customer will spend. As the dataset contains the amount spent by each customer, a regression can be computed, using a number of approaches, to predict what a customer will spend when certain features are known and/or imputed.  

In this notebook, some efforts are made feature selection, including 

 - manual selection
 - model informed selection (from ensembled trees, as in gradient boosted trees and random forests)
 - feature engineering, as in the use of interaction terms (i.e. quadratic terms).
 
Also, the regression is demonstrated, and relative success measured, for three different algorithms: gradient boosted decision trees, random forests, and linear regression.
