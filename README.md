# Industry Practicum 2020

During the months of Jan-Mar, 2020, while pursuing MS in Business Analytics from Purdue University, my team and I worked for our industry partner as part of our industry capstone project. The partner was a New York based Fortune 200 CPG company.

We applied machine learning and prescriptive solutions in ecommerce analytics to achieve following objectives:

  - Developed profitability prediction model at SKU-level granularity; built Tableau based decision support system for 425 ASINs. Model will help business augment marketing and supply chain when dealing with Amazon.com, Inc.
  - Formed new promotional groupings of SKUs for improved marketing as part of Trade Promotion Optimization by implementing profit    optimization using MILP
  - Projected $22 million increase in year-on-year revenue growth by improving sales forecasting by 25% using ARIMA and LSTM
  
## INFORMS Business Analytics Conference 2020, Denver

We were also selected and invited to present our industry poster at this prestigious conference. 

![INFORMS Poster](https://github.com/akshay-madar/industryPracticum-fortune200-CPG-amazonProfitability/blob/master/Industry%20Poster.jpg)

![Presentation](https://github.com/akshay-madar/industryPracticum-fortune200-CPG-amazonProfitability/blob/master/Poster%20Presentation%20at%20Expo.jpg)

### Note:
All necessary data has been hidden or anonymized as per NDA requirements with our industry partner.

## Abstract:
In collaboration with a multinational consumer products company that posts and sells its products on Amazon.com, this project aims to provide the business an enhanced decision support system for identifying profitable as well as underperforming products, using both statistical and machine learning models.
The scope of this project includes all vendors who sell their products on an ecommerce platform and find it challenging to understand the profitability of their product catalog, as compared to selling from a traditional brick-and-mortar retailer. Amazon shares mostly aggregated metrics and often is unwilling to provide more granular measures of where costs arose. For example, advertisement investment is not broken down by the product. There is a lack of clarity regarding how chargeback is performed and how fulfillment costs are derived. Large CPGs do not like working in the dark when the volume of products shipped and sold is massive, which leads to millions in costs.
This work will help them to optimize product strategy and channelize the marketing efforts efficiently, via accurate sales forecasting and profitability prediction at the granular level of stock-keeping units (SKU).

## Modeling:
The nature of the underlying problem, which consisted of time-series data necessitated the use of the following models that could perform time series forecasting. The paper employs both, ARIMA forecasting algorithm and RNN based LSTM models for the purpose of the study.

**LSTM**:

Long Short Term Memory networks, usually called LSTMs, are a special kind of Recurrent Neural Networks, and have the capability to lean long term dependencies, which is crucial for time series forecasting. In addition to a single ‘tanh’ layer in conventional RNN, LSTMs have 4 additional interacting layers as shown in Fig X, which allows them to handle the ‘vanishing gradients’ problem.
On the flip side, LSTMs taken longer to run and occupy more memory to train. It is also vital to include dropout regularization to prevent overfitting, when using multiple LSTM layers. 
For hyperparameter tuning, we controlled the following parameters – epochs, batch size, units, and dropout rate. [6]
 
*LSTM Mechanism:*
<p align="center">
  <img width="560" height="400" src="https://github.com/akshay-madar/industryPracticum-fortune200-CPG-amazonProfitability/blob/master/lstm.png">
</p>


**ARIMA:**

ARIMA or Auto Regressive Integrated Moving Average are a class of models used for forecasting time series data. The ARIMA forecasting equation for a stationary time series is a linear (i.e., regression-type) equation in which the predictors consist of lags of the dependent variable and/or lags of the forecast errors. A nonseasonal ARIMA model is classified as an "ARIMA(p,d,q)" model, where:
•	p is the number of autoregressive terms,
•	d is the number of nonseasonal differences needed for stationarity, and
•	q is the number of lagged forecast errors in the prediction equation.



**Auto ARIMA:**

Pyramid, a python library brings R’s auto.arima functionality to Python. Unlike ARIMA, it uses brute force or stepwise approach [7] to try different combinations of p (auto-regressive), d (time backshift), q (moving average) and returns the best model after evaluation of AIC and BIC. Pyramid operates by wrapping statsmodels.tsa.ARIMA and statsmodels.tsa.statespace.SARIMAX into one estimator class, with a scikit-learn like user interface.


## References:
[1] Ramos, P., Santos, N., Rebelo, R., 2015. Performance of state space and arima models for consumer retail sales forecasting. Robotics and computer-integrated manufacturing 34, 151– 163

[2] Brownlee, J. (2019, August 5). Time Series Prediction with LSTM Recurrent Neural Networks in Python with Keras. Retrieved from https://machinelearningmastery.com/time-series-prediction-lstm-recurrent-neural-networks-python-keras/ 

[3] Eckhardt, K. (2018, November 29). Choosing the right Hyperparameters for a simple LSTM using Keras. Retrieved from https://towardsdatascience.com/choosing-the-right-hyperparameters-for-a-simple-lstm-using-keras-f8e9ed76f046

[4] Calster, T.V., Bossche, F.V., Baesens, B., & Lemahieu, W. (2020). Profit-oriented sales forecasting: a comparison of forecasting techniques from a business perspective. ArXiv, abs/2002.00949. 

[5] Zhang, G. P., Qi, M., 2005. Neural network forecasting for seasonal and trend time series. European journal of operational research 160 (2), 501–514. 

[6] Olah, C. (2015, August 27). Understanding LSTM Networks. Retrieved from https://colah.github.io/posts/2015-08-Understanding-LSTMs/ 

[7] Hyndman, R., & Khandakar, Y. (2008). Automatic Time Series Forecasting: The forecast Package for R. Journal of Statistical Software, 27(3), 1 - 22. doi:http://dx.doi.org/10.18637/jss.v027.i03 
 
