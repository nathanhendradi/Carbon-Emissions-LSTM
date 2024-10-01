# Carbon-Emissions-LSTM
This work involves developing an LSTM (Long Short-Term Memory) model to predict future methane emissions in the United States based on historical data. The goal is to utilize deep learning to forecast future values with high accuracy.
Short Paper Summary: LSTM Model for Predicting Methane Values
Introduction

Data Preparation
The methane emission data is prepared using a window method, where each set of past values predicts the next value. The data is then split into training, validation, and test sets.
Hyperparameter Optimization
Used GridSearchCV tool to optimize key hyperparameters, including the number of neurons, LSTM units, window size, number of layers, and learning rate. The best-performing model is selected based on the lowest mean squared error.
Results
The grid search identifies the optimal configuration of the model for methane emission prediction. The final model achieves competitive performance in predicting future methane values, demonstrating the efficacy of LSTM networks in time-series forecasting.
Best Parameters:
Activation Function: ReLU
Learning Rate (Adam Optimizer): 0.001
LSTM Units: 128
Number of Layers: 3
Number of Neurons per Dense Layer: 128
Window Size: 5
Best Score: -905.65

An LSTM is a type of recurrent neural network (RNN). An RNN is a neural network containing loops that allows information to persist rather than be forgotten about, allowing the model to output a value based on recent info. However, an LSTM has the ability to store long term information, hence the name (Long-Short Term Memory).

The cell-state is the core idea behind the LSTM. It is a dedicated memory pathway that runs along the chain of the neural network, allowing information to flow along it unchanged, enabling the model to retain a memory of important information across long sequences. However, the cell-state can be modified with the use of three gates, allowing info to be removed or added.

LSTMs utilize these gates to regulate the flow of information in and out of the cell state. Each gate is a layer that uses a sigmoid activation function to produce an output that decides what to do with the information.

The first gate is the forget gate, which allows information to be deleted from the cell state. It takes the current input and previous hidden state as inputs and produces a vector of values between 0 and 1. Values close to 0 represent “forget” while values close to 1 represent “retain,” effectively allowing the program to discard information.

The input gate works in tandem with the forget gate, deciding which pieces of the new information are important enough to be added to the cell state, also by producing a vector that controls what new information is allowed in. It acts as a filtration system for the incoming data.

Finally, the tanh layer creates a vector of new values to be added to the cell state. It applies the tanh activation function to the input data, producing a vector of values between -1 and 1. These values are then taken into the input gate and scaled before being added to the cell state.


