# Digit Recognition DNN
 MNIST digit recognition using Deep Neural Network

 Data preparation, exploration, visualization

 The training and test data set are loaded. Exploratory functions such as .describe and .isna are run. Fortunately, both sets have no null values. The training set contains 42000 rows of entries.
 There are 784 columns, each representing a pixel. The values range from 0 to 9, representing the greyscale with 0 being totally white.
 I also printed the first 25 figures, reshaping the array to 28 by 28 matrix and using imshow.
 The label’s distribution is also explored and the training dataset is balanced across 10 labels.

 Review research design and modeling methods

 The training features data is normalized using standard scaler. The same scaler is used to transform the testing data.
 Four different DNN classification models were trained, and all of them are constructed using tensorflow.keras package. Each model contains an input layer consisting of 128 nodes (corresponding to 128 training data columns), and an output layer consisting of 10 nodes (corresponding to 10 labels).

 The difference between different models are the hidden layer:

 Model 1 contains 2 hidden layers with 40 nodes each. Model 2 contains 2 hidden layers with 20 nodes each. Model 3 contains 4 hidden layers with 40 nodes each, and Model 4 contains 4 hidden layers with 20 nodes each. All hidden and input layers use rectified linear activation function (ReLU). And the output layer uses softmax activation fuction.
 The compiled model uses ‘adams’ optimizer, categorical cross entropy as loss function. And the scaled training data is used to fit the model, with epoch=5.
 The time for training each model is recorded.
 
 Predictions are made using testing data and each model trained. A function was used to convert the output softmax lists to the label with maximum probability, using ‘argmax’.
 Review results, evaluate models

 The 2 hidden layer models performed better than 4 hidden layers model, and took less time to train.
