# BackPropagation Neural Network
Implement BackPropagation Neural Network without any machine learning or deep learning package.<br>
<br>

## Introduction
This program is **customizable** with model size and number of neurons.<br>
The changes in **loss** and **weights** during training can be **recorded**, and display when the training finished.<br>
The activation function use **Sigmoid** in hidden layers and **Softmax** in the output layer.<br>
Using **CrossEntropy** as **loss function** and **Adaptive Moment Estimation(ADAM)** as **optimizer**.<br>
Taking simple binary **classification** as a **verification example**, the accuracy 99.53% can be achieved after 252 seconds of training.<br>
<br>

### Class : Fully Connected Layer<br>
Using **Gaussian distribution**(mean=0; Standard Deviation=1) for random **weights initialization**.<br>
Default: **Sigmoid Function** as the **Activation Function** for hidden layer, **Softmax Function** as the **Activation Function** for output layer.<br>
Using **Adaptive Moment Estimation(Adam)** as the **Optimizer** to update the weights and decay the learning rate.<br>
#### This class has the following methods:<br>
  1. Chain Rule Calculation for Back-Propagation
  2. Forward Transform
  3. Update Weights
  4. Show Weights
  5. Reset Derivative
<br>

### Class : Neural Network<br>
Default: **Cross Entropy** as the **Loss Function**.<br>
This class has the following methods:<br>
  1. Input Training Data
  2. Add layers into the model
  3. Forward Transform of the entire model
  4. Loss Function and its derivative
  5. Training with customizable batch size and epoch
  6. Record overall changes in weights and loss
<br>

## Demonstration
### Training Dataset
Building a binary classification problem with 2D features (x, y).<br>
Where -10 < x, y < 10, and the size of dataset = 30000.<br>
If x+y > 2*sin( 2*pi*(x-y) / (10*sqrt(2)) ), it is classified into the first category and labeled as [1, 0].<br>
Otherwise, classify the others into the second category and label them as [0, 1].<br>
The schematic is shown below.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/TrainingDataset.jpg)<br>
<br>
  
### Model Construction
This program can build customized models according to different objects.<br>
Users can tune model parameters to achieve higher accuracy.<br>
```python
# Set batch size and epoch
#-------------------------------------------------------------------------------
batch_size = 1000
epoch = 100

# Create model, set dimension of feature(input) and label(output)
#-------------------------------------------------------------------------------
MyModel = NeuralNetwork( input_size=2, output_size=2, batch_size=batch_size, epoch=epoch )

# Create layer, set dimension of layer input and number of neuron 
#-------------------------------------------------------------------------------
layer1 = FullyConnectedLayer( input_size=2, neuron_size=16 )
layer2 = FullyConnectedLayer( input_size=16, neuron_size=32 )
layer3 = FullyConnectedLayer( input_size=32, neuron_size=2, is_output_layer=True )

# Add layers into the model
#-------------------------------------------------------------------------------
MyModel.AddLayer(layer1)
MyModel.AddLayer(layer2)
MyModel.AddLayer(layer3)

# Input training data to the model
#-------------------------------------------------------------------------------
MyModel.InputTrainingData(training_set)

# Start training, show training time and accuracy
#-------------------------------------------------------------------------------
time_start = time.time()
loss_history, weight_history = MyModel.Train()
print(f"Training Time: {round(time.time()-time_start,5)}s")
print(f"Accuracy: {round((1-loss_history[-1])*100,5)}")
```
<br>

### Training Time and Accuracy
The accuracy of 99.53% can be achieved after 252 seconds of training.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/Accuracy.jpg)<br>
<br>

### Loss and Weights History
The Changes in loss and weights during training can be recorded as shown below.<br>
#### Loss History:<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/LossHistory.jpg)<br>
<br>

#### Weights History:<br>
Weights History collects all weights into a list, and the user can select the layer to be displayed.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/WeightsHistory.jpg)<br>
<br>

### Testing:
Evenly distribute 201*201 points in the interval -10 <= x, y <= 10,<br>
a total of 40401 points to verify the correctness of the model.<br>
And the final classification results are shown in the figure below.<br>
![](https://github.com/TW-ZJLin/Back-PropagationNeuralNetwork/blob/main/Figures/Testing.jpg)<br>
<br>
