# Neural_Networks
## Overview
In this analysis, my client AlphabetSoup has asked me to use machine learning models to help their foundation determine which organizations they should fund, in order to optimize the success of their investments. Using a deep learning model and the TensorFlow library, I have created a binary classifier which determines whether an investment is likely to be successful or not, based on a number of variables. 
## Results
### Data Preprocessing
#### What variable(s) are considered the target(s) for your model?
- IS_SUCCESSFUL

#### What variable(s) are considered to be the features for your model?
- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- SPECIAL_CONSIDERATIONS
- ASK_AMT

#### What variable(s) are neither targets nor features, and should be removed from the input data?
- EIN
- NAME

### Compiling, Training, and Evaluating the Model
#### How many neurons, layers, and activation functions did you select for your neural network model, and why?
I chose the following numbers based on a series of optimizations that produced the highest accuracy when the model was evaluated against the testing data.

- Neurons: 175
- Layers: 3
- Activation Functions: Relu, Sigmoid (Output function)

![Optimization1](https://github.com/luke-c-newell/Neural_Network_Charity_Analysis/blob/main/images/Optimization1.png "Optimization1.png")

#### Were you able to achieve the target model performance?
I was not able to achieve the target model performance of 75%. I was able to reach a performance of 72.9%, achieved during Optimization 1.

#### What steps did you take to try and increase model performance?
##### Optimization 1
- Added an additional hidden layer with the relu activation function
- Added additional neurons to the first and second hidden layers
- Reduced the number of epochs
- Changed the number of bins for the application type and classification columns

##### Optimization 2
- Changed the output activation function to tanh
- Reduced the number of neurons in the hidden layer
- Changed the number of bins for the application type and classification columns

##### Optimization 3
- Dropped the INCOME_AMT variable from the features
- Added additional neurons to the first and second hidden layers
- Changed the output activation function to selu
- Added an additional hidden layer
- Changed the activation functions for the initial hidden layers
- Changed the output activation function to selu

## Summary
After evaluating the best performing model (Optimization 1) against the test data, the following results were obtained: 
- Loss: 0.549, 
- Accuracy: 0.729
Overall, this model does not reach the target accuracy of 75%. In order to produce a model that could reach the desired accuracy of 0.75, the RandomForestClassifier model could be used. This model may produce a more accurate result as it can handle the tabular data used in this analysis and uses a number of weak learners to predict the classification based on the consensus of all learners.
