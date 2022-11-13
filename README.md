# Unit 21 Homework: Analysis

## Overview

My task was to help the nonprofit foundation, Alphabet Soup, decide which ventures it should fund, based each venture's likelihood of success. I used the information provided by Alphabet Soup about its past projects, along with my knowledge of machine learning and neural networks, to create a binary classifier that could predict whether an applicant will be successful.

## Results

### *Data Preprocessing*
* What variable(s) are the target(s) for your model?
    * IS_SUCCESSFUL
    ![X and y assignments](/Images/OriginalModel/Xy.png)
* What variable(s) are the features for your model?
    * APPLICATION_TYPE
    * CLASSIFICATION
    * USE_CASE
    * ORGANIZATION
    * STATUS
    * INCOME_AMT
    * SPECIAL_CONSIDERATIONS
    * ASK_AMT
* What variable(s) should be removed from the input data because they are neither targets nor features?
    * EIN and NAME
    ![Dropped Columns](/Images/OriginalModel/DroppedColumns.png)

### *Compiling, Training, and Evaluating the Model*
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
    * I decided to use an input layer, one hidden layer, and an output layer to build my neural network. Three layers are enough to produce a good, but not overly complex model.
    * For the first two layers, I used the relu function because it has shown to be more effective than the signmoid function in most cases. For the output layer, I chose the sigmoid function because it seemed to produce better results in this instance. The signmoid function is also particularly well suited for two possible target outcomes.
    ![Model Structure](/Images/OriginalModel/ModelStructure.png)
* Were you able to achieve the target model performance?
    * I was not able to achieve the target model performance.
    ![Evaluation](/Images/OriginalModel/Evaluation.png)
* What steps did you take in your attempts to increase model performance?
    * I increased the number of epochs used to train the model from 20 to 200.
    ![Optimized Model Epochs](/Images/OptimizedModel/OptimizedModelEpochs.png)
    * I added two extra hidden layers to my model.
    ![Optimized Model Structure](/Images/OptimizedModel/OptModelBuilding.png)
    * I changed the activation function from relu to sigmoid in the first three layers of my model. For the output layer, I chose to switch to the relu function from sigmoid.
    * I added a hyperparameter search to determine the optimal number of units in each densely-connected layer and the optimal learning rate for the optimizer.
    ![Hyperparameter Search](/Images/OptimizedModel/HyperparamSearch.png)
    * I dropped the following two noisy layers:
        * STATUS
        * SPECIAL_CONSIDERATIONS
        ![Drop Noisy Variables](/Images/OptimizedModel/DropNoisyVars.png)

## Summary

### *Overall Results*
I was able to create a model that predicted which ventures would succeed, with an accuracy of 0.7278. This model involes an input layer, three hidden layers, and an output layer. The input layer and two of the hidden layers use a sigmoid function, while the third hidden layer and the output layer use the ReLU function.

![Optimized Model Evaluation](/Images/OptimizedModel/EvalOptimizedModel.png)

A better model might involve more hidden layers and might involve removing more variables. The income amount column also appears to contain messy data. To improve my model more, I could try removing the income amount column to see if it produces better results.