# Deep-Learning-in-NLP
Introduction to Deep Learning in NLP

Task
Steps:
Set the trainable parameters (TIP: np.random.rand)
Set the learning rate (0.01 will do, but you can try others and see what changes), the number of epochs (full passes through the dataset)
Make a linear transformation through the first layer (the first set of weights)
Apply some nonlinear activation function (tanh, relu)
Make a linear transformation through the second layer (the second set of weights)
Apply sigmoid
Calculate the loss function (binary cross entropy), do not forget to average over the batch
Save the values ​​of the loss function in the 'losses' array
Take derivatives of the loss function for each trainable parameter video about derivatives
Update the weights w1, b1, w2, b2 using the gradient descent
Visualize the loss function
TIP: the number of input features is 784 (28 pixels * 28 pixels)
TIP: in step 0, multiply w1, w2 by 0.01, and initialize b1, b2 to zeros. This is not the best implementation, but we don't know a better way yet
TIP: in backward, the loss function for your model's predictions needs to be divided by the number of examples in the batch (don't forget that you are averaging the loss)
TIP: calculate each subsequent gradient by multiplying by the previous one, that is, you don't need to calculate for each layer and then merge everything. You need to calculate the gradient for d_L/d_z2 as d_L/d_y_hat multiplied by d_y_hat/d_z2 at once, where y_hat is our predictions.
If you find it difficult, do it for one layer first
Hints for dimensions
Forward
z1 - first linear transformation - (BATCH_SIZE, INNER_FEATURES)
a1 - nonlinearity application - (BATCH_SIZE, INNER_FEATURES)
z2 - second nonlinear transformation - (BATCH_SIZE, 1)
pred - sigmoid - (BATCH_SIZE, 1)
loss - loss function - scalar
Backward
d_loss/d_pred - gradient of loss function by pred - (BATCH_SIZE, 1)
d_loss/dz2 - gradient of sigmoid by z2 - (BATCH_SIZE, 1)
d_loss/da1 - gradient of linear transformation by a1 - (BATCH_SIZE, INNER_FEATURES)
d_loss/dw2 - gradient of linear transformation by w2 - (INNER_FEATURES, 1)
d_loss/db2 - gradient of linear transformation by b2 - (1,)
d_loss/dz1 - gradient of nonlinear function by z1 - (BATCH_SIZE, INNER_FEATURES)
d_loss/dw1 - gradient of linear transformation by w1 - (IN_FEATURES, INNER_FEATURES)
d_loss/db1 - gradient of linear transformation by b1 - (INNER_FEATURES,)

