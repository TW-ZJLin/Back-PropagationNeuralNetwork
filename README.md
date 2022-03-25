# Back-PropagationNeuralNetwork
Implement Back-Propagation Neural Network without any machine learning and deep learning package.<br>

## Introduction
This program is customizable with the number of layers in the model, and the number of neurons in the layers.<br>
The Changes in loss and weights during training can be recorded, and display their records when the training finished.<br>
The activation function use Sigmoid in hidden layers and Softmax in the output layer.<br>
The model use CrossEntropy as loss function and Adaptive Moment Estimation(ADAM) as optimizer.<br>


### Class : Fully Connected Layer<br>
This class has the following methods:<br>
  1. Chain Rule Calculation for Back-Propagation
  2. Update Weights
  3. Show Weights
  4. Reset Derivative
  5. Optimizer with Adaptive Moment Estimation (Adam)
  6. Activation Function with Sigmoid Function

### Class : Neural Network<br>
This class has the following methods:<br>
  1. Input Training Data
  2. Add layers into the model
  3. Loss Function with Cross Entropy
  4. Loss Function with Mean Square Error (MSE)
  5. Training
