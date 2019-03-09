# Intorduction to TensoFLow
## Basic Tensorflow Functions
The following doc recaps the basic functions to deploy a simple Neural Network using `TensorFlow` and `keras` on `python`. Steps to code a full simple NN.

#### The imports
Define the tools you will use:
* **TensorFlow framework** - `tensorflow`
* **MatPlot Library** - `matplotlib`
* **Numpy Library** - `numpy`

```python
# TensorFlow Framework
import tensorflow as tf
#  Pyplot to plot images
import matplotlib.pyplot as plt
# Numpy Library
import numpy as np
```
#### Load Dataset (Using MNIST)
* **Datasets** - `tf.keras.datasets.fashion_mnist` 
* **Load Data** - `mnist.load_data()`

```python
# Mnist
mnist = tf.keras.datasets.fashion_mnist
# Load data
(training_images, training_labels), (test_images, test_labels) = mnist.load_data()
```

#### Plot Data
* **Show Image** - `plt.imshow()`

```python
plt.imshow(training_images[23])
```

#### Normalization
```python
training_images = training_images / 255.0
test_images = test_images / 255.0
```

#### Model Definition
Define the Neural Network composition. Layers, units, activation functions.
* **Model Definition** - `models.Sequential()`
* **Learnin Process Definition** - `model.compile()`

```python
# model definition
model = tf.keras.models.Sequential([tf.keras.layers.Flatten(), 
                                    tf.keras.layers.Dense(512, activation=tf.nn.relu), 
                                    tf.keras.layers.Dense(10, activation=tf.nn.softmax)])
# model compilation
model.compile(optimizer = tf.train.AdamOptimizer(),
              loss = 'sparse_categorical_crossentropy',
              metrics=['accuracy'])
```

#### Training
* **Process the training** - `model.fit()`

```python
# Train the model
# epochs define the number of iterations for the lerning process
model.fit(training_images, training_labels, epochs=40)
```

#### Evaluate
* **Evaluate test data** - `model.evaluate()`

```python
model.evaluate(test_images, test_labels)
```

#### Predict. Use the Neural Network

* **Use the Neural Network** - `model.predict()`

```python
model.predict(sample[3]);
```

> **NOTES** - 
* For simple data, increase the number of layers usually has no significant impact
* For more complex data, like color images, adding more layers will be necessary
* For simple data, adding neurons can usually have a good impact.


