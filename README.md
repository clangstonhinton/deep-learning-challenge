# deep-learning-challenge
Use neural network deep learning to predict non-profit applicants' success 

<img width="1200" alt="Screen Shot 2023-04-29 at 2 02 43 AM" src="https://user-images.githubusercontent.com/44728723/235286788-96767064-3118-48e0-b2d0-37e3ec74ef26.png">

## Overview of the Analysis
The purpose of this analysis was to build a neural network machine learning model for the nonprofit foundation Alphabet Soup to help it select the applicants for funding with the best chance of success in their ventures. A binary classifer neural network model was built to predict whether applicants will be successful if funded by Alphabet Soup. A target accuracy of 75% was set for the classifer.

### Data Description:
 - The dataset contains information for more than 34,000 organizations that have received funding from Alphabet Soup over the years. The metadata contains 12 columns including: EIN, NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT, and IS_SUCCESSFUL.

 - The "target" variable for the model is the "IS_SUCCESSFUL" column indicating if the money was used effectively or not. A value of "0" indicates that the grant money was NOT used effectively. A "1" indicates that the grant money WAS used effectively. 

### Approach:
 1. Data Preprocessing:
    - The EIN and NAME colums were removed from the input data as these data were not viewed as targets nor features.
    - For APPLICATION_TYPE and CLASSIFICATION feature columns which have more than 10 unique values, a cutoff point to bin "rare" categorical variables into an "other" category was determine. APPLICATION_TYPE values were cutoff at 500 and CLASSIFICATION values were cut off at 300.
    - The data were split into labels (the predicted target value of "IS_SUCCESSFUL") and features (remaining columns).
    - The data were split into training and testing sets using scikit learn train_test_split function and scaled using StandardScaler.

 2. Original Model Run:  
 An original Neural Network model was compiled, traned and evaluated for accuracy based on the followign parameters.
    - Hidden Layers = 2
    - Number of Nodes in Hidden Layers = 32 nodes each
    - Hidden Layer Activation Function = relu
    - Batch Size = 32
    - Epochs = 30
    - Model Optimizer = adam
    
 3. Optimizing the Model:
 A tuner test was run to allow the kerastuner to select from the below hyperparameters and determine the most optimal model. Then the optimized model was run on the original dataset (same dataset as the Original Model) and the accuracy and loss metrics were calculated.
    - Number of Hidden Layers between 1 and 5
    - Number of Nodes in each hidden layer
    - Hidden Layer Activation Function between relu and tanh
    - Number of Epochs between 10, 20, 30, 40, 50, and 60
    - Model Optimzer between adam, adagrad, rmsprop, and sgd
    

## Results

### 1. Original Model:  
The Original Model had an accuracy of 0.727 with a loss of 0.555. The model was trained and evaluated on data that excluded the EIN and NAME columns. The model construct included: 
  - Hidden Layers = 2
  - Number of Nodes in Hidden Layers = 32 nodes each
  - Hidden Layer Activation Function = relu
  - Batch Size = 32
  - Epochs = 30
  - Model Optimizer = adam

<img width="450" alt="Screen Shot 2023-04-29 at 3 39 34 AM" src="https://user-images.githubusercontent.com/44728723/235290483-11894972-6088-4bc6-9097-7425f3dc4865.png">

### 2. Model v2: 
For Model v2, the "NAME" column was added to the dataset as a feature to determine if the organization name could improve the model's accuracy. The "EIN" and "STATUS" colummns were removed. Model v2 was less accurate than the original model with an accuracy of 0.581 and a loss of 0.709. The model construct replicated that of the Original Model above to hold all other potential influencers constant.

<img width="450" alt="Screen Shot 2023-04-29 at 10 30 03 AM" src="https://user-images.githubusercontent.com/44728723/235308242-36ecdca3-3b44-46f4-9197-d2e220e49586.png">

### 3. Optimized Model: 
In the Optimized Model, the hyperparameters were optimized based on the results of the tuner testing. The Optimized Model performed similarly to the Original Model with an accuracy of 0.728 and a loss of 0.553. The model construct included: 
  - Hidden Layers = 5
  - Number of Nodes in Hidden Layers:
    - Hidden Layer 1:  26 nodes
    - Hidden Layer 2:  26 nodes
    - Hidden Layer 3:  11 nodes
    - Hidden Layer 4:  21 nodes
    - Hidden Layer 5:  11 nodes
  - Hidden Layer Activation Function = tanh
  - Batch Size = 32
  - Epochs = 20
  - Model Optimizer = adam

### Summary:
Overall the models failed to reach the target accuracy of 75%. A Random Forest classifier may be a better choice as it is a robust modeling approach and could provide increased accuarcy due to its sufficient number of estimators and tree depth. 












