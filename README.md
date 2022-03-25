# BackPropagation Neural Network
Implement Back-Propagation Neural Network without any machine learning and deep learning package.<br>

## Introduction
This program is **customizable** with the number of layers in the model, and the number of neurons in the layers.<br>
The Changes in **loss** and **weights** during training can be **recorded**, and display their records when the training finished.<br>
The activation function use **Sigmoid** in hidden layers and **Softmax** in the output layer.<br>
The model use **CrossEntropy** as **loss function** and **Adaptive Moment Estimation(ADAM)** as **optimizer**.<br>
Taking simple binary **classification** as a **verification example**, the accuracy of 99.64% can be achieved after 17.67 seconds of training.<BR>

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

## Implement
### Training Dataset
Building a binary classification problem with 2D features (x, y).<br>
Where -10 < x, y < 10, and the size of dataset = 20000.<br>
If x+y>0, it is classified into the first category and labeled as [1, 0].<br>
Otherwise, classify the others into the second category and label them as [0, 1].<br>
The schematic is shown below.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/TrainingDataset.jpg)<br>

### Training Time and Accuracy
The accuracy of 99.64% can be achieved after 17.67 seconds of training.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/Accuracy.jpg)<br>

### Loss and Weights History
The Changes in loss and weights during training can be recorded as shown below.<br>
#### Loss History:<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/LossHistory.jpg)<br>

#### Weights History:<br>
Weights History collects all weights into a list, and the user can select the layer to be displayed.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/WeightsHistory.jpg)<br>

### Testing:
Evenly distribute 201*201 points in the interval -10 <= x, y <= 10,<br>
a total of 40401 points to verify the correctness of the model.<br>
And the final classification results are shown in the figure below.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/Testing.jpg)<br>
  
  
  


