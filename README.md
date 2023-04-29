# deep-learning-challenge
Use neural network deep learning to predict non-profit applicants' success 

<img width="1200" alt="Screen Shot 2023-04-29 at 2 02 43 AM" src="https://user-images.githubusercontent.com/44728723/235286788-96767064-3118-48e0-b2d0-37e3ec74ef26.png">

## Overview of the Analysis
The purpose of this analysis was to build a neural network machine learning model for the nonprofit foundation Alphabet Soup to help it select the applicants for funding with the best chance of success in their ventures. A binary classifer neural network model was built to predict whether applicants will be successful if funded by Alphabet Soup.

### Data Description:
 - The dataset contains information for more than 34,000 organizations that have received funding from Alphabet Soup over the years. The metadata contains 12 columns includind: financial loan data across 8 feature columns, including: EIN, NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT, and IS_SUCCESSFUL.

 - The "target" variable for the model is the "IS_SUCCESSFUL" column indicating if the money was used effectively or not. A value of "0" indicates that the grant money was NOT used effectively. A "1" indicates that the grant money WAS used effectivelu. ***Is the target variable  BALANCED or UNBALANCED? ***The original "loan_status" data were unbalanced with 75,036 values of "0" (healthy loans) and 2,500 values of "1" (high risk of defaulting loans).

### Approach:
 1. Data Preprocessing:  
  - The data were preprocessed and split into labels (the predicted target value of "IS_SUCCESSFUL") and features (remaining columns).
  - The EIN and NAME features (or columns) were removed from the input data as these data were not viewed as targets nor features.
  - The data were split into training and testing sets using scikit learn train_test_split function.
 2. Original Model Run:  Original Neural Network model was compiled, traned and evaluated for accuracy.
    - # of neurons
    - # of hidden layers
    - activation functions
    - # of epochs
    - optimizer
 3. Optimizing the Model
  - Were you able to achieve the target model performance?
    - What steps did you take in your attempts to increase model performance?
Using TensorFlow, the model was optimized to achieve a target predictive accuracy higher than 75%. 


## Results

Below are the results of the two logistic regression models deployed in the analysis.

### 1. Original Model:  Accuracy: 0.727  Model_Loss:  0.555

<img width="450" alt="Screen Shot 2023-04-29 at 3 39 34 AM" src="https://user-images.githubusercontent.com/44728723/235290483-11894972-6088-4bc6-9097-7425f3dc4865.png">


Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
