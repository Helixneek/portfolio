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

# Rock-Paper-Scissors Classifier

Rock-Paper-Scissors Classifier is a convolutional neural network (CNN) model that classifies images of hands. The CNN model detects whether the image given is of a "rock", "paper", or "scissors" hand shape. The model is written in Python using Tensorflow and Keras libraries.&#x20;

The dataset used is the Rock-Paper-Scissors dataset provided by Dicoding. After training and testing, the model has 96.48% accuracy and 96.58% validation accuracy. This model was compiled with the "categorical crossentropy" loss function, "Adamax" optimizer and uses accuracy as its metric.

{% hint style="info" %}
This project was an assignment for Dicoding's Machine Learning path.
{% endhint %}

```python
notebook-python
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(32, (3,3), activation='relu', input_shape=(150, 150, 3)),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(64, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(128, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(256, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(512, activation='relu'),
    tf.keras.layers.Dense(3, activation='softmax')
])
```

***

{% embed url="https://colab.research.google.com/drive/1RvvDKHrYSWS1x9SThPpIb9hX8P_O_Em3?usp=sharing" %}
