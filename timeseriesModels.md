
# Types
ARIMA, Prophet, LSTMs, CNNs, GPVAR, Seasonal Decomposition, DeepAR, and more

* consider your options before committing to a model

# Two main considerations
* local or global 
* univariate or multivariate

## Local univariate
* A local model (aka an iterative or traditional model) only uses the prior values of a single data column to predict future values. 
* Local models only rely on a single data column, must also be univariate, predicting a single variable over time.

### Use cases:
1. Data is trivial
If data is simple, univariate, and easy to predict, a classical approach to time series prediction may be best. 

* It can be trained immediately, 
* requires little computing resources, 
* more complex models may be overkill and overfit your data. 

    Example: predicting how many of a certain item will be sold in a store.

2. Need accurate predictions but only have 1 variable
* only have 1 usable variable, iterative forecasting/ensemble local models have proven time and time again that they can predict data more accurately than many ML models due to their ability to negate the downsides and weaknesses of any one particular model, 
* training may be relatively expensive, it remains one of the most popular methods of time series forecasting. 

    Example of this is predicting the stock market using past data.

3. Models that are predictably seasonal
If it is known the data follows predictable seasonal patterns, many time series such as SARIMA (Seasonal Autoregressive moving average) is built to handle data when you are confident in what your “season” is. 
    Example of this may be web traffic, it is known data follows a regular pattern on a daily basis. Can define a model with daily seasonality.

### Local Univariate models (from simplest to most complex)

* Moving Average -- Simplest method and can be computed with 1 line of pandas

* Exponential Smoothing/Holt-Winters — Exponential Smoothing predicts values using a weighted average of all previous values, where more recent values are weighted higher. In Holt-Winters, seasonality and trends are taken into the equation as parameters

* ARIMA/SARIMA/Auto-ARIMA — At its base, it is a derivative of a moving average plus an autoregressive term (using past values with noise) in order to predict future values. SARIMA takes into consideration seasonality and Auto-ARIMA will perform a search to try and find the optimal model parameters

* Prophet — a regression model that incorporates a linear or logistic growth trend, seasonal components, and changepoint detection. has ability to separate out these trends and plot them for you!








## Global model 
uses many data columns to predict future values, generally time-independent variables. 


### global univariate
use many values to predict a single value

Eg: use MaxTemp, Evaporation, and Humidity to predict the future maxTemp value


### global multivariate
use many values to predict many values

Eg: utilize MaxTemp, Evaporation, and Humidity to predict the future value of MaxTemp, Evaporation, and Humidity


### Use Cases 
1. Have a lot of supplementary variables and are looking to predict many or all of the values in the future
2. If unaware of the seasonality or trends of the model
3. Need to train many time series for many different variables, all wrapped into a single model efficiently


### Global Models
* SARIMAX - ARIMA (discussed earlier) that takes into account exogenous (outside) variables to allow the time series to adapt to changing variables faster
* Tree - Trees can be thrown at almost every problem with some success. advantageous if data is sparse. They are accurate, and are relatively fast to train in comparison to deep methods
* MLP - classic fully-connected neural network
* CNN - Convolutional Neural Networks are similar to MLPs except they are not fully connected. CNNs are widely used because they tend to be smaller, less wasteful, and easier to train.
* RNN/LSTM -  RNNs are neural networks that “loop” into each other. The reason this works so well is it allows subsequent data points to “remember” what has already been processed in the few preceding points allowing for more dynamic predictions, as time series are naturally dependent on the previous values.

# reference:
https://towardsdatascience.com/choosing-the-best-ml-time-series-model-for-your-data-664a7062f418