# goldtrendprediction
The neural network that predicts a change in the trend of the price of gold.
The selection for last 15 years of gold 1 hour price data was splited in 3 groups: the price was rising, the price was standing still and the price was falling.
Each group included almost 33% of all selection, so the random forecast would be 33%.

The selection was saturated with additional data: some of patterns of Japanese candlesticks, values derivatives, second derivatives, inverse values and others (you can find more details in goldtrendprediction_pynb.ipynb). 

The neural net architecture was chosen from about 20 alternatives which includes but not limited to lstm, convlstm, cnn, etc.
The preferred architecture TCN with 2 hidden layers shows the best result: 38.77% accuracy on validation selection and 42.75% on testing selection for gold which is almost 10% above random.

The trained for gold neural net was also tested on bitcoins 1 hour data and the result is 41.38% which is more then 8% above random.

There exist also multiple ways to improve the accuracy: find and train 1 min data with this architecture or saturate the selection with additional data.

To use this neural net you should repeat the repeat the steps described in goldtrendprediction_pynb.ipynb for initial price data, create the model with architecture as in file goldtrendprediction_pynb.ipynb and load weights to the model.

checkpoint_filepath = '/right_data_tcn_500ep_xBatch_5000_xLen_200_github'
model.load_weights(checkpoint_filepath) #upload best weights to the model
