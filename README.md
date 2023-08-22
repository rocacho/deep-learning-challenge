# deep-learning-challenge
Module 21 Challenge

# Module 21 Challenge Report

## Overview

The purpose of this analysis was to create a deep learning model  that serves as a tool that can help the nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures. The model aims to classify whether the funding provided will be used effectively (IS_SUCCESSFUL: Was the money used effectively) based on various features provided in the dataset such as APPLICATION_TYPE—Alphabet Soup application type, AFFILIATION—Affiliated sector of industry,CLASSIFICATION—Government organization classification, USE_CASE—Use case for funding, ORGANIZATION—Organization type, STATUS—Active status, INCOME_AMT—Income classification, SPECIAL_CONSIDERATIONS—Special considerations for application, ASK_AMT—Funding amount requested

![Alt Text](images/Data_Frame.png)

## Results

I was not able to achieve an accuracy higher than 75% with non of my attempts. Below you will find a description of the attemps performed in this project: 

### Original Model

#### Data Preprocessing

- Target variable(s): IS_SUCCESSFUL
- Feature variable(s): All features excluding EIN, NAME
- Removed variables: EIN, NAME

#### Compiling, Training, and Evaluating the Model

- Neurons: 80 in 1 hidden layer with activation function 'relu'
- Result: Loss - 0.5809, Accuracy - 0.7285

![Alt Text](images/Original_Model.png)

### Optimization Attempt 1: Dropping More Columns

#### Data Preprocessing

- Target variable(s): IS_SUCCESSFUL
- Feature variable(s): All features excluding EIN, NAME, and ASK_AMT
- Removed variables: EIN, NAME, ASK_AMT

#### Compiling, Training, and Evaluating the Model

- Neurons: 80 in 1 hidden layer with activation function 'relu' (mantained the same as the original model)
- Result: Loss - 0.5556, Accuracy - 0.7300

![Alt Text](images/Attempt_1.png)

### Optimization Attempt 2: Creating More Bins for Rare Occurrences

#### Data Preprocessing 

- Mantained the same as the original model
-- Target variable(s): IS_SUCCESSFUL
-- Feature variable(s): All features excluding EIN, NAME
-- Removed variables: EIN, NAME

#### Compiling, Training, and Evaluating the Model

- Bins Created for: ASK_AMT
- Neurons: 80 in 1 hidden layer with activation function 'relu'(mantained the same as the original model)
- Result: Loss - 0.5602, Accuracy - 0.7276

![Alt Text](images/Attempt_2.png)

### Optimization Attempt 3: More Hidden Layers, Neurons & Activation Functions

#### Data Preprocessing 

-- Target variable(s): IS_SUCCESSFUL
-- Feature variable(s): All features excluding EIN, NAME, ASK_AMT
-- Removed variables: EIN, NAME, ASK_AMT

#### Compiling, Training, and Evaluating the Model

- Neurons: 200 in 4 hidden layers - (50, 'relu'), (50, 'relu'), (50, 'tanh'), (50, 'tanh')
- Result: Loss - 0.5574, Accuracy - 0.7289

![Alt Text](images/Attempt_3.png)

## Summary

The origial deep learning model was initially built using only one hidden layer and 80 neurons, achieving an accuracy of 72.85%. With the several optimization attempts, I managed to observe improvements to the accuracy, but those imporvements wher very very slight. One option that seemd to imporve a bit more the accuracy was dropping more columns that led to the highest accuray I got with 73.00%.  On the other hand, creating more bins did not result in significant accuracy improvements. An other attempt that took me a lot of adjusments involved introducing more hidden layers, additional neurons, and different activation functions, but the accuracy was not changing significantly even if I add 200 neurons (i een tried with 300) or more layers, the result I got was 72.89%.

Considering the above mentioned information the best results I got was a Loss of 0.556 indicating the capacity of my model to predictions the actual target values by quantifies the difference between predicted values and actual values. ANd an accuracy of 0.7300 means that the model is making accurate predictions for approximately 73.3% of the instances

## Recommendation for a Different Model

For this classification problem, we have to manage a very complex data set. A good first alternative that poped into my maind was to use decision trees, due to the visualization it porvides a good process but it could be very complex to execute and explain. Maybe a model such as Random Forest could help in this case, the pros and cons of Random Forest as seen in clas are:

###Random Forest: Generate n number of trees, an take votes for each prediction

#### Pros:
- You dont need to standarize your data
- They are easy to explain
- They are powerful

#### Cons:
- We are not able to gnerate visual data such as in the the tree visualization
