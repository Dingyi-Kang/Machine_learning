In RNN (Recurrent Neural Network) models for time series forecasting, it is generally a good practice to normalize or standardize the feature data, including the target variable you want to predict. This is because RNNs, like other neural networks, are sensitive to the scale of input data.

Normalization usually involves rescaling the data to a specific range, typically [0, 1], while standardization adjusts the data to have zero mean and unit variance. There are different methods to normalize or standardize data, such as Min-Max scaling and Z-score standardization.

### note:
When normalizing or standardizing the data, remember to fit the scaler only on the training data and then apply the same transformation to both training and testing data to avoid data leakage.

After the model has made predictions, you should inverse-transform the predictions back to their original scale to interpret the results and compare them to the true values.

### for MAE -- especially for RNN, since the input and output could be same feature, if you don't normalize predict data and input data is also scaled
Even if the loss function is Mean Absolute Error (MAE), normalizing or standardizing the feature data is still a good practice for the reasons mentioned earlier. 

RNNs, like other neural networks, are sensitive to the scale of input data due to the nature of their internal operations and the activation functions used in the hidden layers. The sensitivity to input data scale is not directly related to the choice of the loss function, such as MAE, but rather to the architecture and training process of the neural networks.

Here are some reasons why RNNs are sensitive to the scale of input data:

Weight initialization: Neural networks, including RNNs, typically use small random values to initialize weights. If the input data is on a large scale, the activations of the neurons can become very large or very small, leading to slower learning or vanishing/exploding gradients.

Activation functions: Many activation functions, such as sigmoid or tanh, are sensitive to the scale of their input values. When the input values are large or small, these functions tend to saturate, leading to small gradients and slow learning.

Optimization algorithms: Most optimization algorithms used for training neural networks, such as stochastic gradient descent (SGD) or Adam, rely on gradient information to update the weights. If the input data is not normalized or standardized, the gradients can vary significantly across different input dimensions, leading to inefficient learning and difficulties in convergence.

Numerical stability: The scale of input data can also affect numerical stability during the training process. For example, large input values might lead to large activations and gradients, causing numerical overflow or underflow issues.

Using MAE as the loss function does not negate the need for normalization or standardization, as it is not directly related to these aspects of neural network training. While the derivative of MAE is indeed the sign function, it only affects how the model optimizes the weights in response to the error, not the internal workings of the RNN itself.
