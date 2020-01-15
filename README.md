# Convolutional-Neural-Networks
Coursera Course: https://www.coursera.org/learn/convolutional-neural-networks/home/welcome

1.1 One Layer of CNN
- Without CNN number of parameters needed for a NN layer=(image width*image height*number of channel (RGB has three)+1 (bias))* number of neurons in the layer
- WIth CNN number of parameters needed for a layer= (filter size * filter size * number of channel+ 1 (bias))* number of filters
- Ouput volumn n(l)_H*n(l)_W*n(l)_c. n_H=(n(l-1)_H+2*padding-filter_size)/stride +1; Same for n_H. n(l)_c=number of filters 
- Padding increase size of volumn by 2*padding, it doesn't affect the number of channels
- Output volume after padding: n_H*n_W*n_c. (n_H-filter_size)/stride+1; same for n_W; number of channel doesn't change

1.2 Max pooling
- Even pooling layers don not have parameters, they DO affect the backpropagation (derivatives) calculation; Even though a pooling layer has no parameters for backprop to update, you still need to backpropagation the gradient through the pooling layer in order to compute gradients for layers that came before the pooling layer.

1.3 Why CNN
- Parameter sharing: It reduces athe total number of parameters, thus reducing overfitting; it allows a feature detector to be used in multiple locations throughout the whole input image/input volume
- Sparsity of connections: each activation in the next layer depends on only a small number of activations from the previous layer.

1.4 Convolution Model step by step project
  - [Convolution Model step by step Link](Convolution_model_Step_by_Step_v2a.ipynb)

1.5 Convolution model Application project
 - [Convolution model Application Link](Convolution_model_Application_v1a.ipynb)

2.1 Facts about very deep ConvNet
 - In order to be able to build very deep networks, we usually only use pooling layers to downsize the height/width of the activation volumes while convolutions are used with “SAME” padding. Otherwise, we would downsize the input of the model too quickly.
 
 2.2 ResNet
 - The skip-connection makes it easy for the network to learn an identity mapping between the input and the output within the ResNet block.
 - Using a skip-connection helps the gradient to backpropagate and thus helps you to train deeper networks
 - A ResNet with L layers would have on the order of L/2 (L divided by 2) skip connections in total. 

 2.3 Inception NN
 - Inception blocks usually use 1x1 convolutions to reduce the input data volume’s size before applying 3x3 and 5x5 convolutions.
 - A single inception block allows the network to use a combination of 1x1, 3x3, 5x5 convolutions and pooling.
 - Making an inception network deeper (by stacking more inception blocks together), the performance increase and then decrease (or the error decrease and then increase). Only ResNet performance always increase.

 2.4 Practical advise - using open-source implementations of ConvNets
 - It is a convenient way to get working an implementation of a complex ConvNet architectue
 - Parameters trained for one computer vision task are often useful as pretraining for other computer vision tasks.
 - The same techniques for winning computer vision competitions, such as using multiple crops at test time, are used at benchmark and winning competitions, but are NOT usually used in practical deployments (or production system deployments) of ConvNets (due to increased computation cost)

2.5 Keras Tutorial
  - [Keras Tutorial Link](Keras_Tutorial_v2a.ipynb)

2.6 Residual Networks
 - [Residual Networks Link](Residual_Networks_v2a.ipynb)

3.1 Detection Algorithms
 - YOLO Algorithm: INPUT {Pc, by, bh, bw, C1, C2, C3,...Cn} Pc=1 if exist the object, Cx=1 if object x present. If the object has a known size, bn and bw can be neglect. OUTPUT volume= X*Y*a*(n+5). X*Y is sieze of grid. n is number of classes. 5 comes from Pc and bx,by,bh,bw
 - No-max suppression: discard all box with Pc<=threshold1. Discard any remaining box with IOU>=threshold2. IOU is intersection of uion=size of intersection/size of uion.
 
3.2 Autonomous_driving_application_Car_detection Project
- [Autonomous_driving_application_Car_detection Link](Autonomous_driving_application_Car_detection_v3a.ipynb)
