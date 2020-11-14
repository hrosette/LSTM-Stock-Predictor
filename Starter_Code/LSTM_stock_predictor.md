# LSTM Stock Predictor


In this assignment, I built and evaluated deep learning models using both FNG values (a public sentiment indicator for cryptocurrencies) and closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

Specifically, I used historic Bitcoin closing and sentiment data for my recurrent neural network model.


The lstm_stock_predictor_fng file uses the FNG values to try and predict the closing price of bitcoin.
The lstm_stock_predictor_closing file uses previous closing prices to try and predict the next closing price for bitcoin.

Each model used 70% of the data for training and 30% of the data for testing.


Based on the results, the following questions can be answered:

* Which model has a lower loss?

The closing price predictor model had a lower loss than the FNG pridictor model.

* Which model tracks the actual values better over time?

The closing price predictor model tracks the actual values better over time.

* Which window size works best for the model?

FNG 10 day window loss = .1255
Closing 10 day window loss = .0067

FNG 1 day window loss = .093
Closing 1 day window loss = .00159

FNG 5 day window loss = .087
Closing 5 day window loss =.007

The window size of 1 day works best for the model.
