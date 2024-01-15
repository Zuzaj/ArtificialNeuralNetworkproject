
<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->
<h1 align="center">🤖🧠 Artificial Neural Network 🧠🤖 </h1>


<!-- TABLE OF CONTENTS -->
<details>
  <summary> ✏️Table of Contents</summary>
  <ol>
    <li>
      <a href="#authors">Authors</a>
    </li>
    <li>
      <a href="#topic">Topic</a>
    </li>
    <li><a href="#datasets">Datasets</a>
       <ul>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## 	👩 Authors 👨

Our group consists of 2 people:
* Martyna Baran
* Zuzanna Jarlaczyńska


<!-- GETTING STARTED -->
## 💡 Topic
An Artificial Neural Network (ANN) is a graph of nodes (or neurons) connected by links. Neurons are organised in layers so that the outputs of neurons in one layer serve as inputs to neurons in the next layer. An ANN as a classification or regression nonlinear model is capable of accumulating knowledge (learning) about its coefficients and structure through an algorithm (backpropagation algorithm). After the learning process, our network is able to approximate a continuous function, which is supposed to be our decision rule.

## 🎯 Objective
The aim of our project is to implement the multilayer perceptron to solve regression and classification
problems. The neural network should be implemented with generic number of hidden layers and neurons. 

</br>

# 🛠️ Implementation
The neural network consists of three types of classes: InputLayer, HiddenLayer, and the overall NeuralNetwork class.
</br>
## Activation Function
The sigmoid activation function is used throughout the network. We define 2 functions:
* **sigm** - sigmoid function used in forward propagation of inputs
* **sigm_delta** - the derivative of simgoid function nueeded for back propagation
</br>

## Layer Classes

### InputLayer(Layer)
The InputLayer class represents the initial layer of the neural network, corresponding to the input features.
* **Attributes**:
  * **outputs** - matrix of output weights
  * **neurons_num** - number of neurons equal to the size of input data   
### HiddenLayer(Layer)
The HiddenLayer class represents the hidden layers of the neural network. 
* **Attributes**:
  * **outputs** - matrix of output weights
  * **neurons_num** - number of neurons initialized in the constructor
* **Methods**:
  * **backpropagation**(self, next_layer) 
  * **propagateInputs**(self, prev_layer) - propagates inputs through the hidden layer
  * **accumulateChange**(self, prev_layer) - accumulates weight changes for the hidden layer
  * **adjustWeights**(self, prev_layer, lr, u) - adjusts weights based on accumulated changes, learning rate (lr) and momentum (u)
</br>

## Neural Network
The NeuralNetwork class represents the entire artificial neural network.
* **Attributes**:
  * **inputs** - matrix of patterns for training
  * **outputs** - real outputs
  * **layers** - network's layers
  * **output** - predicted output weights for current input pattern
  * **d** - real output for current input pattern
  * **layers_num** - # of layers
  * **neurons_per_layer** - list of # of neurons per layer
* **Methods**:
  * **init**(self, inputs, real_outputs, layers_num, neurons_per_layer=[])- initializes the neural network with input patterns, real outputs, and desired architecture
  * **add**(self, layer: Layer) -  adds a layer to the neural network
  * **init_weights**(self) -  initializes weights for each layer in the neural network
  * **backpropagateError**(self) - implements backpropagation of error through the neural network
  * **forward**(self) - implements forward propagation through the neural network
  * **Change**(self) - accumulates weight changes for the entire neural network
  * **Weights**(self, lr, u) - adjusts weights for the entire neural network
  * **feed_input**(self, input, output) - feeds input pattern and real output to the neural network
  * **train**(self, epochs, lr, u) - trains the neural network for a specified number of epochs
  * **predict**(self, pattern, output) - makes predictions for a given input pattern and real output


<!-- USAGE EXAMPLES -->
## 📖 Datasets 

The databases are the following:

### XOR Regression
This dataset represents the non-linear XOR classification problem. The training and test sets will be the same with a total of four patterns, with two inputs and one output per pattern. It should be noted that the same file is used for training and generalization because having such a small number of patterns it would be very complicated to train with two and generalize well with the other two.

### Digits Classification
This database consists of a set of digits between 0 and 9, handwritten by different people. The digits are adjusted to images of 16 x 16 pixels so we will have a total of 256 binarized input variables. As what is intended is the correct classification from the entries in the represented number, we will have ten outputs per pattern (1 for each number between 0 and 9). In this case we have a training database with a total of 1274 patterns, and a test database with a total of 319 patterns. 

### Format
The format of the datasets is as follows:
* The first line shows the total number of problem inputs (k), the total number
of problem outputs (J) and the total number of patterns (N).
* Then we will have N lines, corresponding to each pattern.
* Each of the lines will have k + J real values.
    * k values refer to the inputs of the problem for that pattern.
    * J values refer to the outputs of the problem for that pattern.
We created additional function **load_dataset** to deal with this format. 
<p align="right">(<a href="#readme-top">back to top</a>)</p>




