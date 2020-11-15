# LSTM Stock Predictor

## Background Information 

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the Crypto Fear and Greed Index (FNG) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. 

In this assignment, I built and evaluated a deep learning recurrent neural networks to model bitcoin closing prices. One model uses the FNG indicators to predict the closing price while the second model uses a window of closing prices to predict the nth closing price. The goal is to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

## Preparing the data for training and testing

* For the Fear and Greed model, I used the FNG values to try and predict the closing price. 
* For the closing price model, I used previous closing prices to try and predict the next closing price. 
* Each model uses 70% of the data for training and 30% of the data for testing.
* A MinMaxScaler was used to the X and y values to scale the data for the model.
* Finally, I reshaped the X_train and X_test values to fit the model's requirement of samples, time steps, and features. (example: `X_train = X_train.reshape((X_train.shape[0], X_train.shape[1], 1))`)

## Build and train custom LSTM RNNs

In each Jupyter Notebook, the same custom LSTM RNN architecture is used. In one notebook, the FNG values data is used to train the model while in the second notebook, the closing prices data is used to train the model.

The same parameters and training steps are used for each model. This is necessary to compare each model accurately.
 * epochs = 50
 * batch size = 10
 * dropout_fraction = .2
 * number_units = .2

## Evaluate the performance of each model

**Key Findings:**

* The closing price predictor model had a lower loss than the FNG pridictor model. A loss function is a measure of how good a prediction model does in terms of being able to predict the expected outcome.
* The closing price predictor model tracks the actual values better over time.
* The window size of 1 day works best for the model. As shown below:

    FNG 10 day window loss = .1255 Closing 10 day window loss = .0067

    FNG 1 day window loss = .093 Closing 1 day window loss = .00159

    FNG 5 day window loss = .087 Closing 5 day window loss =.007

