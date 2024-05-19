# Neural Network Model Optimization Report

## Overview of the Analysis

The purpose of this analysis is to build and optimize a deep neural network model to predict whether applicants will be successful if funded by Alphabet Soup based on various features. The target accuracy for the model is higher than 75%. Multiple strategies, including adjusting input data, adding more neurons and layers, changing activation functions, and tuning training parameters, were employed to achieve this goal.

## Results

* Target Variable(s):
   
    * The target variable for the model is 'IS_SUCCESSFUL' column, which indicates whether a donation campaign was successful (1) or not (0).

* Feature Variable(s):
   
   * 'APPLICATION_TYPE'(Alphabet Soup application type)
   *  'AFFILIATION'(Affiliated sector of industry)
   * 'CLASSIFICATION'(Government organisation classification)
   * 'USE_CASE'(Use case for funding)
   * 'ORGANIZATION'(Organisation type)
   * 'INCOME_AMT'(Income classification)
   * 'SPECIAL_CONSIDERATIONS'(Special considerations for application)
   * 'ASK_AMT(Funding amount requested)

* Removed Variable(s):
   
   * The EIN and NAME columns were removed as they are identifiers and do not contribute to the prediction of the target variable.

## Compiling, Training, and Evaluating the Model

## Neural Network Model (1) Configuration:

* Number of Neurons and Layers:
     
     1. First Hidden Layer: 5 neurons, ReLU activation.
     2. Second Hidden Layer: 3 neurons, ReLU activation.
    3. Output Layer: 1 neuron, Sigmoid activation
* Activation Functions:
    
    * The rectified linear unit (ReLU) or rectifier activation function introduces the property of nonlinearity to a deep learning model and solves the vanishing gradients issue.
    * Sigmoid activation function was used for the output layer to predict a probability for the binary classification task.

`Model: "sequential"
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃ Layer (type)                    ┃ Output Shape           ┃       Param # ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ dense (Dense)                   │ (None, 5)              │           210 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_1 (Dense)                 │ (None, 3)              │            18 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_2 (Dense)                 │ (None, 1)              │             4 │
└─────────────────────────────────┴────────────────────────┴───────────────┘
 Total params: 232 (928.00 B)
 Trainable params: 232 (928.00 B)
 Non-trainable params: 0 (0.00 B)`

 * Compilation and Training:
    
     * The model was compiled using the binary_crossentropy loss function, which is suitable for binary classification tasks, and the Adam optimizer.

     * The model was trained for 100 epochs.

## Neural Network Model (2) Configuration:

* Number of Neurons and Layers:
     
     1. First Hidden Layer: 128 neurons, ReLU activation.
     2. Second Hidden Layer: 64 neurons, ReLU activation.
     3. Third Hidden Layer: 32 neurons, ReLU activation
    4. Output Layer: 1 neuron, Sigmoid activation
* Activation Functions:
    
    * The rectified linear unit (ReLU) or rectifier activation function introduces the property of nonlinearity to a deep learning model and solves the vanishing gradients issue.
    * Sigmoid activation function was used for the output layer to predict a probability for the binary classification task.

`Model: "sequential_1"
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃ Layer (type)                    ┃ Output Shape           ┃       Param # ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ dense_3 (Dense)                 │ (None, 128)            │         5,376 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_4 (Dense)                 │ (None, 64)             │         8,256 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_5 (Dense)                 │ (None, 32)             │         2,080 │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense_6 (Dense)                 │ (None, 1)              │            33 │
└─────────────────────────────────┴────────────────────────┴───────────────┘
 Total params: 15,745 (61.50 KB)
 Trainable params: 15,745 (61.50 KB)
 Non-trainable params: 0 (0.00 B)
 `
 * Model Performance:

     * This model was trained for 200 epochs.
     * The final test accuracy achieved:
     `268/268 - 0s - 723us/step - accuracy: 0.7238 - loss: 0.6151
Loss: 0.615125834941864, Accuracy: 0.7238484025001526`

* Optimization Steps:
   
    *  Increased the number of neurons in each layer to enhance the model's capacity to learn complex patterns.
    * Added a third hidden layer to increase the depth of the model.
    * Trained the model for more epochs to allow it to learn better.

## Conclusion:
   * he optimized neural network model with three hidden layers achieved a test accuracy of 0.72%. Although the target accuracy of 75% was not met, significant improvements were made through various optimization techniques.

## Resources

1. I have sought assistance from the support staff at Ask BCS.
2. I found that utilizing class activities was beneficial for completing my homework.
3. IRS. Tax Exempt Organization Search Bulk Data Downloads.
4. [RELU function](https://www.google.com/search?q=relu+function&oq=RELU+&gs_lcrp=EgZjaHJvbWUqBwgCEAAYgAQyBggAEEUYOTIHCAEQABiABDIHCAIQABiABDIHCAMQABiABDIHCAQQABiABDIHCAUQABiABDIHCAYQABiABDIHCAcQABiABDIHCAgQABiABDIHCAkQABiABNIBCDY3NTZqMGo3qAIIsAIB&sourceid=chrome&ie=UTF-8).
5. [sigmoid function](https://www.google.com/search?q=sigmoid+function&sca_esv=345267d81bec8f30&sca_upv=1&sxsrf=ADLYWIIB-JmctTXXPuMEq48yDFiB67Rgsg%3A1716117727339&ei=3-BJZv2UFOvYseMPiOanyA0&oq=sig+function&gs_lp=Egxnd3Mtd2l6LXNlcnAiDHNpZyBmdW5jdGlvbioCCAAyBhAAGAcYHjIGEAAYBxgeMgYQABgHGB4yBhAAGAcYHjIGEAAYBxgeMgYQABgHGB4yBhAAGAcYHjIGEAAYBxgeMgYQABgHGB4yBhAAGAcYHkj0JVDJDFjUGnACeAGQAQCYAZcCoAGrC6oBBTAuMy40uAEDyAEA-AEBmAIHoALKB8ICChAAGLADGNYEGEfCAg0QABiABBiwAxhDGIoFwgILEAAYgAQYkQIYigXCAg4QABiABBiRAhixAxiKBcICERAAGIAEGJECGLEDGIMBGIoFwgIIEAAYgAQYsQPCAgUQABiABMICCBAAGAcYChgewgIKEAAYgAQYQxiKBZgDAIgGAZAGCpIHBTIuMy4yoAelKA&sclient=gws-wiz-serp)