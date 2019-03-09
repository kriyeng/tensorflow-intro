# Introduction to TensorFlow
## Basic Intro Concepts

#### Machine Learning
Thanks to an input data and answers you obtain a rules to apply to new data.
#### Neural Network
Network of neurons that computes an input to produce an output. There's an input layer, a defined number of hidden layers and output layer. Every layer has a number of units, called neurons. 
Every neuron has what's called `activation function`. An `activation function` is something like a filter that decides how much every neuron will participate in the whole network based on the values receiving. 
#### Training NN
You need to train a NN in order to obtain the best rules that produce your desired output. To train a NN you need a dataset with training labeled data. 
Training a NN means to use your NN on the training data and check the results you obtain thanks to your actual rules. Then you check your differences between the output you obtained and the output you want to achieve. We apply to this difference what's called a `loss function`. `loss function` allows you to _parametrize_ your difference in some way in order to be more computable or normalized to be comparable. This `loss function` will be your rating value to know how good your NN is doing. This is done using a `loop`. This loop steps are the following
  1. Compute your inputs with your NN to obtain an output
  2. Get your `loss` value
  3. Modify your parameters slightly to improve your results
  4. Back to step 1. until you consider your result is good enough.
The way you retouch your parameters in your NN is not random. You use what's called `back propagation`. `back propagation` uses mathematical tool (derivatives mainly) in order to obtain in which direction you hace to retouch your parameters in order to improve your result.
#### Optimizers
An optimizer is an algorithm that improve the way you retouch your parameters on every iteration of the training loops.
#### Loss Function
An algorithm that allow you to know how good your **rules** are.

