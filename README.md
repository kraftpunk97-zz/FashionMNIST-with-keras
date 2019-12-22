# FashionMNIST-with-keras
Tackling the [FashionMNIST dataset](https://github.com/zalandoresearch/fashion-mnist) with convolutional neural networks from keras and tensorflow.

This notebook is a result of my experimentation with keras, which is something I've been wanting to try for a long time. I don't really like TensorFlow because I feel its way of doing things is way too convoluted. [keras](https://keras.io) is an API that sits on top of TensorFlow and uses a relatively easy-to-understand syntax, so that we don't have to deal with the guts of TensorFlow; keras takes care of it for us.

In this notebook, we will be tackling the Fashion MNIST dataset. We will be training three increasingly complex CNNs and then we populate our dataset using data augmentation techniques and further train the three models on the augmented dataset.

We use three Convolutional Neural Networks...

<ol>

<li>

1-Conv Model`model_cnn1`)

(`conv_layer11`)\[ Conv ---> MaxPool ----> DropOut] ----><br>
Unroll ----><br>
(`dense_layer11`)\[ Dense -----> Dense ]

</li>

<li>

3-Conv Model(`model_cnn2`)

(`conv_layer21`)\[ Conv ---> MaxPool ---> DropOut] ---><br>
(`conv_layer22`)\[ Conv ---> MaxPool ---> DropOut] ---><br>
(`conv_layer23`)\[ Conv ---> DropOut] ---><br>
Unroll ---><br>
(`dense_layer21`)\[ Dense ----> DropOut ] ---><br>
(`dense_layer22`)\[ Dense ]

</li>

<li>

4-Conv Model(`model_cnn3`)

(`conv_layer31`)\[Conv --> BatchNorm] --> <br>
(`conv_layer32`)\[Conv --> BatchNorm --> MaxPool --> DropOut] => <br>
(`conv_layer33`)\[Conv --> BatchNorm --> Dropout] ---> <br> (`conv_layer34`)\[Conv --> BatchNorm --> MaxPool --> DropOut]  => <br>
Unroll --> <br>
(`dense_layer31`)\[Dense --> BatchNorm --> DropOut] --> <br>(`dense_layer32`)\[Dense --> BatcNorm --> DropOut] --> <br>(`dense_layer33`)\[Dense]

</li>
</ol>

The accuracy of the models of on the Cross-validation set of the unaugmented set of images is shown below
<img src="https://i.imgur.com/r87alsV.png">
