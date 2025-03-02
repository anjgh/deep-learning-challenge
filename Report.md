## Overview
The purpose of this analysis is to develop a deep learning model to determine the success of charity applications. The goal is to create a model that can accurately predict whether a charity application will be successful based on the various features of the application. This analysis involves data preprocessing, model training, and evaluation to improve the model's performance and achieve the given target performance.

## Results
### Data Preprocessing 

- `IS_SUCCESSFUL` is the target variable for the model
- The feature varibles for the models are all the other columns within the DataFrame. This inlcludes;
    - `APPLICATION_TYPE`
    - `AFFILIATION`
    - `CLASSIFICATION`
    - `USE_CASE`
    - `STATUS`
    - `INCOME_AMT`
    - `SPECIAL_CONSIDERATIONS`
    - `ASK_AMT`

- The variables `EIN` and `NAME` were removed from the input data since they are not important to the accuracy of the model. 

### Compiling, Training, and Evaluating the Model

- Orginal Model
    - First Layer: 80 neurons, ReLu activation
    - Second Layer: 30 neurons, ReLU activation
    - Output Layer: 1 neuron, Sigmoid activation

- Optimized Model
    - First Layer: 512 neurons, ReLu activation
    - Second Layer: 256 neurons, ReLU activation
    - Third Layer: 128 neurons, ReLU activation
    - Forth Layer: 64 neurons, ReLU activation
    - Output Layer: 1 neuron, Sigmoid activation

- The original model was not able meet the model performance target of 75%. 
- The following steps were taken in order to increase the performance of the model
    - Increased the number of layers of the model and nueorons within those layers
    - Added batch normalization to layers after each dense layer to nortmalize the activations of the previous layer, to stabilize and speed up training
    - Added early stopping callback to monitor the validation loss and stop training when the performance stops improving, to prevent overfitting and reduce training time 

## Summary
The model was designed to predict the success of charity applications. The original model had a simple architechture with two hidden layers, it did not meet the performance target of 75% accuracy. Several steps were taken to improve the model's performance including, increasing the number of layers and neurons, batch normalization and early stopping. Despite these improvements, the optimized model still did not achieve the desired performance target of 75%.