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

# News Article Classifier Model

News Article Classifier is a convolutional neural network (CNN) model that classifies news articles based of their content, such as business, sports, finance, etc. The model is written in Python using Tensorflow and Keras libraries. This model utilizes LSTM (Long Short-Term Memory) layers to help with processing the text.&#x20;

The dataset used is hgultekin's BBC News Archive dataset on [Kaggle.](https://www.kaggle.com/datasets/hgultekin/bbcnewsarchive) After training and testing, the model has 99.44% accuracy and 93.26% validation accuracy. This model was compiled with the "categorical crossentropy" loss function, "Adam" optimizer and uses accuracy as its metric.

<pre class="language-python"><code class="lang-python"><strong>model = tf.keras.Sequential([
</strong>        tf.keras.layers.Embedding(input_dim=10000, output_dim=32),
        tf.keras.layers.LSTM(128),
        tf.keras.layers.Dense(128),
        tf.keras.layers.Dropout(0.5),
<strong>        tf.keras.layers.Dense(5, activation='softmax')
</strong>])
</code></pre>

***

{% embed url="https://colab.research.google.com/drive/19fswgysDPu9Ih0jII-OBcHpHVBSOZqZc?usp=sharing" %}
