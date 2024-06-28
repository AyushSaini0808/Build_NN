# BUILDING A NEURAL NETWORK FROM SCRATCH

## INTRODUCTION
--------

A neural network is the foundation of many deep learning applications. Moreover in all of the deep learning projects we simply use the NN models present in famous packages such as Tensorflow and Keras and therefore we observe the superficial working the model. Thorugh this notebook i would like to highlight the important procedures that are involved in a neural network

## Dataset
---------
The dataset utilised in the notebook is the MNIST dataset , a famous computer vision dataset . The link for the dataset is given as follows : [dataset](https://www.kaggle.com/competitions/digit-recognizer/data)

The data files train.csv and test.csv contain gray-scale images of hand-drawn digits, from zero through nine.

Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive.

The training data set, (train.csv), has 785 columns. The first column, called "label", is the digit that was drawn by the user. The rest of the columns contain the pixel-values of the associated image.

Each pixel column in the training set has a name like pixelx, where x is an integer between 0 and 783, inclusive

