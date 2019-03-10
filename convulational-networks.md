# Introduction to TensorFlow
## Convulational Nerual Networks
CNN is a techinque we apply to our basic Neural Netowrks in order to improve the analysis of our data. We try to detect features in a better way and we also try to reduce our data to improve the speed of our algorithms.

### Concepts
#### Convulation
A convulation is a filter we apply to our data (images) in order to emphisize some aspects of it. We define a custom size of the filter to apply on every pixel and its neighbours. 
#### Pooling
Pooling allows us to reduce/compress our data but without removing the features on it. We apply some pool of defined sized and apply some algorithm on it. For instance we can get the most significant value (the highest) of the pool.

### How to apply on TensorFlow

#### Convulation

Keras layers gives us a method to apply Convultational layers to our NNs.
**Conv2D()** - Accepts the following basic parameters:
  1. Number of filters 
  2. Shape of the filter. (width, height)
  3. Activation function - `activation=`
  4. Input shape - `input_shape=`

Usage: 
```python
tf.keras.layers.Conv2D(64, (3,3), activation='relu', input_shape=(28, 28, 1))
```

> NOTES: 
* Ouput dimensions: When we apply a Convulation to images, we can apply to every corner and edges of the images due to fact that edge pixels has no enough pixels in the neighbourhood to apply the entire box. For instance, we can't apply a 3x3 filter on the pixel (0,0). We need to start applying on the (1,1), loosing 1 pixel on the top, bottom and sides of the image. Is for this reason that an Convulation input shape of (28, 28) will output a shape of (26, 26). Exists some tricks to add fake pixels on edges to allow us starting for the pixel (0, 0) 


#### Pooling
Keras layers gives us a method to add some Polling layers to our NN.
**MaxPooling2D()** - Accepts the following basic parameters:
  1. Shape of the pool. (width, height)

Usage: 
```python
tf.keras.layers.MaxPooling(2, 2)
```

#### Model Summary
When you have defined your Neural Network you can print all the details with `keras` using `model.summary()`

>_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_3 (Conv2D)            (None, 26, 26, 32)        320       
_________________________________________________________________
max_pooling2d_3 (MaxPooling2 (None, 13, 13, 32)        0         
_________________________________________________________________
flatten_3 (Flatten)          (None, 5408)              0         
_________________________________________________________________
dense_6 (Dense)              (None, 256)               1384704   
_________________________________________________________________
dense_7 (Dense)              (None, 10)                2570      
=================================================================
Total params: 1,387,594
Trainable params: 1,387,594
Non-trainable params: 0
_________________________________________________________________
