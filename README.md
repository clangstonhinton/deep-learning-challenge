# deep-learning-challenge
Use neural network deep learning to predict non-profit applicants' success 

<img width="1200" alt="Screen Shot 2023-04-29 at 2 02 43 AM" src="https://user-images.githubusercontent.com/44728723/235286788-96767064-3118-48e0-b2d0-37e3ec74ef26.png">

## Overview of the Analysis
The purpose of this analysis was to build a neural network machine learning model for the nonprofit foundation Alphabet Soup to help it select the applicants for funding with the best chance of success in their ventures. A binary classifer neural network model was built to predict whether applicants will be successful if funded by Alphabet Soup.

### Data Description:
 - The dataset contains information for more than 34,000 organizations that have received funding from Alphabet Soup over the years. The metadata contains 12 columns including: EIN, NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT, and IS_SUCCESSFUL.

 - The "target" variable for the model is the "IS_SUCCESSFUL" column indicating if the money was used effectively or not. A value of "0" indicates that the grant money was NOT used effectively. A "1" indicates that the grant money WAS used effectively. ***Is the target variable  BALANCED or UNBALANCED? ***The original "loan_status" data were unbalanced with 75,036 values of "0" (healthy loans) and 2,500 values of "1" (high risk of defaulting loans).

### Approach:
 1. Data Preprocessing:  
  - The data were preprocessed and split into labels (the predicted target value of "IS_SUCCESSFUL") and features (remaining columns).
  - The EIN and NAME colums were removed from the input data as these data were not viewed as targets nor features.
  - For APPLICATION_TYPE and CLASSIFICATION feature columns which have more than 10 unique values, a cutoff point to bin "rare" categorical variables into an "other" category was determine. APPLICATION_TYPE values were cutoff at 500 and CLASSIFICATION values were cut off at 300.


# Choose a cutoff value and create a list of classifications to replace with 'Other'
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

### 1. Original Model:  
The Original Model had an accuracy of 0.727 with a loss of 0.555. The model was trained and evaluated on data that excluded the EIN and NAME columns. The model construct included: 
 - 2 hidden layers
 - 32 nodes in each hidden layer
 - Each hidden layer employed "relu" as the activation function
 - 32 batch size
 - 30 epochs
 - Employed "adam" as the model optimizer

<img width="450" alt="Screen Shot 2023-04-29 at 3 39 34 AM" src="https://user-images.githubusercontent.com/44728723/235290483-11894972-6088-4bc6-9097-7425f3dc4865.png">

### 2. Second Model with Different Columns:  
For the 2nd Model, the "NAME" column was added to the dataset as a feature because...XXXXX. The "EIN" and "STATUS" colummns were removed because ....XXXXX. The second model had an accuracy of XXXX with a loss of XXXX. The model construct replicates that of the Original Model above.

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
