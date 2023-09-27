---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Gold Price Forecasting Test Model

Gold Price Forecasting Model is a convolutional neural network (CNN) model that forecasts gold prices over a certain period of time. The model accomplishes this by creating a time series with the model's prediction. The model is written in Python using Tensorflow and Keras libraries. This model utilizes LSTM (Long Short-Term Memory) layers to help with processing the numerical data.&#x20;

The dataset used is arashnic's Learn Time Series Forecasting From Gold Price dataset on [Kaggle. ](https://www.kaggle.com/datasets/arashnic/learn-time-series-forecasting-from-gold-price)After training and testing, the model has 61.86 MAE and 143.256 validation MAE. This model was compiled with the "Huber" loss function, "Adam" optimizer and uses MAE as its metric. The optimizer has a learning rate of 0.0001.

```
model = tf.keras.models.Sequential([
      tf.keras.layers.LSTM(128, return_sequences=True),
      tf.keras.layers.LSTM(64, return_sequences=True),
      tf.keras.layers.Dropout(0.3),
      tf.keras.layers.Dense(30, activation='relu'),
      tf.keras.layers.Dense(1),
      tf.keras.layers.Lambda(lambda x: x * 400),
    ])
```

***

{% embed url="https://colab.research.google.com/drive/1sQL0bDCg7suBhwCLbIB9JsRsNMM6MdkK?usp=sharing" %}
