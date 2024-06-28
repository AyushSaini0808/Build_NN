# BUILDING A NEURAL NETWORK FROM SCRATCH

## INTRODUCTION
--------

A neural network is the foundation of many deep learning applications. Moreover in all of the deep learning projects we simply use the NN models present in famous packages such as Tensorflow and Keras and therefore we observe the superficial working of the model. Through this notebook i would like to highlight the important procedures that are involved in a neural network

## Dataset
---------
The dataset utilised in the notebook is the MNIST dataset , a famous computer vision dataset . The link for the dataset is given as follows : [dataset](https://www.kaggle.com/competitions/digit-recognizer/data)

The data files train.csv and test.csv contain gray-scale images of hand-drawn digits, from zero through nine.

Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive.

The training data set, (train.csv), has 785 columns. The first column, called "label", is the digit that was drawn by the user. The rest of the columns contain the pixel-values of the associated image.

Each pixel column in the training set has a name like pixelx, where x is an integer between 0 and 783, inclusive.

## WORKING 

Our NN will have a simple two-layer architecture. Input layer  𝑎[0]
  will have 784 units corresponding to the 784 pixels in each 28x28 input image. A hidden layer  𝑎[1]
  will have 10 units with ReLU activation, and finally our output layer  𝑎[2]
  will have 10 units corresponding to the ten digit classes with softmax activation.

Forward propagation

𝑍[1]=𝑊[1]𝑋+𝑏[1]
 
𝐴[1]=𝑔ReLU(𝑍[1]))
 
𝑍[2]=𝑊[2]𝐴[1]+𝑏[2]
 
𝐴[2]=𝑔softmax(𝑍[2])
 
Backward propagation

𝑑𝑍[2]=𝐴[2]−𝑌
 
𝑑𝑊[2]=1𝑚𝑑𝑍[2]𝐴[1]𝑇
 
𝑑𝐵[2]=1𝑚Σ𝑑𝑍[2]
 
𝑑𝑍[1]=𝑊[2]𝑇𝑑𝑍[2].∗𝑔[1]′(𝑧[1])
 
𝑑𝑊[1]=1𝑚𝑑𝑍[1]𝐴[0]𝑇
 
𝑑𝐵[1]=1𝑚Σ𝑑𝑍[1]
Parameter updates

𝑊[2]:=𝑊[2]−𝛼𝑑𝑊[2]
 
𝑏[2]:=𝑏[2]−𝛼𝑑𝑏[2]
 
𝑊[1]:=𝑊[1]−𝛼𝑑𝑊[1]
 
𝑏[1]:=𝑏[1]−𝛼𝑑𝑏[1]
 
Vars and shapes

* Forward prop

𝐴[0]=𝑋 : 784 x m </br>
𝑍[1]∼𝐴[1] : 10 x m</br>
𝑊[1]: 10 x 784 (as  𝑊[1]𝐴[0]∼𝑍[1])</br>
𝐵[1]: 10 x 1</br>
𝑍[2]∼𝐴[2]: 10 x m</br>
𝑊[1]: 10 x 10 (as  𝑊[2]𝐴[1]∼𝑍[2])</br>
𝐵[2]: 10 x 1</br>

* Backprop</br>
𝑑𝑍[2] : 10 x m (𝐴[2])</br>
𝑑𝑊[2]: 10 x 10</br>
𝑑𝐵[2]: 10 x 1</br>
𝑑𝑍[1]: 10 x m (  𝐴[1])</br>
𝑑𝑊[1]: 10 x 10</br>
𝑑𝐵[1]: 10 x 1
