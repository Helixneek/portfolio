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

# Bottle Image Classifier Model

Bottle Image Classifier is a convolutional neural network (CNN) model that classifies images of bottles. The CNN model detects what type of bottle it is. It detects water bottles, soda bottles, wine bottles, plastic bottles and beet bottles. The model is written in Python using Tensorflow and&#x20;

The dataset used is the vencerlanz09's Synthetic Bottle Images dataset on [Kaggle](https://www.kaggle.com/datasets/vencerlanz09/bottle-synthetic-images-dataset). After training and testing, the model has 92.6% accuracy and 92.13% validation accuracy. This model was compiled with the "categorical crossentropy" loss function, "Adam" optimizer and uses accuracy as its metric.

```python
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(32, (3,3), activation='relu', input_shape=(150, 150, 3)),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(64, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(128, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(128, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dropout(0.25),
    tf.keras.layers.Dense(512, activation='relu'),
    tf.keras.layers.Dropout(0.25),
    tf.keras.layers.Dense(5, activation='softmax')
])
```

***

{% embed url="https://colab.research.google.com/drive/13mkeo3YGGICBpmG8zfRzoC5bKnuAWdjS?usp=sharing" %}
