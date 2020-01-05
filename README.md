# Convolutional-Neural-Networks
Coursera Course: https://www.coursera.org/learn/convolutional-neural-networks/home/welcome

1.1 One Layer of CNN
- Without CNN number of parameters needed for a NN layer=(image width*image height*number of channel (RGB has three)+1 (bias))* number of neurons in the layer
- WIth CNN number of parameters needed for a layer= (filter size * filter size * number of channel+ 1 (bias))* number of filters
- Ouput volumn n(l)_H*n(l)_W*n(l)_c. n_H=(n(l-1)_H+2*padding-filter_size)/stride +1; Same for n_H. n(l)_c=number of filters 
- Padding increase size of volumn by 2*padding, it doesn't affect the number of channels
- Output volume after padding: n_H*n_W*n_c. (n_H-filter_size)/stride+1; same for n_W; number of channel doesn't change

1.2 Max pooling
- Even pooling layers don not have parameters, they DO affect the backpropagation (derivatives) calculation

1.3 Why CNN
- Parameter sharing: It reduces athe total number of parameters, thus reducing overfitting; it allows a feature detector to be used in multiple locations throughout the whole input image/input volume
- Sparsity of connections: each activation in the next layer depends on only a small number of activations from the previous layer.
