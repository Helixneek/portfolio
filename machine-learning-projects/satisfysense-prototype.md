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

# SatisfySense Prototype

SatisfySense is a convolutional neural network (CNN) model that classifies images of faces. The CNN model detects what emotion is present in the image of the face. The model is written in Python using Tensorflow and Keras libraries. The model is currently in its prototype stage.&#x20;

The dataset used is the mouadriali's AffectNet sample dataset on Kaggle. The dataset is currently unreachable. Currently, training and testing has resulted in 31.72% accuracy and 24.97% validation accuracy. This model was compiled with the "categorical crossentropy" loss function, "Adam" optimizer and uses accuracy as its metric. The optimizer has a learning rate of 0.0001.

SatisfySense was made for my Artificial Intelligence college assignment.

<pre class="language-python"><code class="lang-python">from tensorflow.keras import regularizers
from tensorflow.keras.applications import ResNet50
from tensorflow.keras.applications import ResNet152V2

model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(128, (3,3), activation='relu', padding='same', input_shape=(img_height, img_width, 3)),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.BatchNormalization(),
<strong>    tf.keras.layers.Dropout(0.25),
</strong>
    tf.keras.layers.Conv2D(128, (3,3), activation='relu', padding='same', kernel_regularizer=regularizers.l2(0.1)),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.BatchNormalization(),
    tf.keras.layers.Dropout(0.25),

    tf.keras.layers.Conv2D(256, (3,3), activation='relu', padding='same', kernel_regularizer=regularizers.l2(0.1)),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.BatchNormalization(),
    tf.keras.layers.Dropout(0.25),

    tf.keras.layers.Flatten(),

    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.BatchNormalization(),
    tf.keras.layers.Dropout(0.25),

    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.BatchNormalization(),
    tf.keras.layers.Dropout(0.25),

    tf.keras.layers.Dense(class_num, activation='softmax')
])
</code></pre>

***

{% embed url="https://www.canva.com/design/DAFOXUAqk94/1eIFDHJohQu_CAX8A0lx6g/edit?utm_content=DAFOXUAqk94&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton" %}

{% embed url="https://colab.research.google.com/drive/1KzZH51zAjQ5xH7Mk2LUifYg6y_xbxgu9?usp=sharing" %}
