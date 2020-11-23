# Neural Network CharityAnalysis

## Overview: 
- The purpose of this analysis was to create a machine learning model that can predict whether a company would receive funding from Alphabet Soup depending on a variety of metadata including: application type, affiliation, classification, use case, asking amount, status, organization type, etc..

## Results:
### Data Preprocessing
- What variable(s) are considered the target(s) for your model?
  - The target variable for the model was whether or not the funding was successful (IS_SUCCESSFUL)

- What variable(s) are considered to be the features for your model?
  - Model features include the input parameters, which were the column headers in the merged dataframe after dropping the target value (including application type, classification, income amount, use case, etc..) These features could be identified using the following code: `X = merged_df.drop(["IS_SUCCESSFUL"],1).values`

- What variable(s) are neither targets nor features, and should be removed from the input data?
  - Data that was considered excess "noise" were "EIN" and "NAME", both of which were dropped from the input data in the preprocessing step: `application_df = application_df.drop(columns=['EIN','NAME'])`

### Compiling, Training, and Evaluating the Model
- How many neurons, layers, and activation functions did you select for your neural network model, and why?
  - I attempted to fit multiple different variations of models, and selected neuron counts ensuring the  rule of thumb (2-3x the amount of neurons per number of inputs) is satisfied. In general, I performed modeling using 1-3 hidden layers, and both "relu" and "sigmoid" activation functions.
  
  ![ScreenShots](/Resources/sequential_model.PNG)
  
  ![ScreenShots](/Resources/sequential_model2.PNG)
  
- Were you able to achieve the target model performance?
  - I was not able to achieve the target model performance of 75% after attempting 3 different model variants, but I was able to achieve 74.xx% accuracy using a model with relu activation function and 3 hidden layers. This is an improvement over the initial 53% accuracy from the original sequential model.
  
    ![ScreenShots](/Resources/original_model.PNG)
  
    ![ScreenShots](/Resources/final_model3.PNG)
    
- What steps did you take to try and increase model performance?
  - In order to optimize model performce, I first tried to drop extraneous variables from the input data. Then, I adjusted the number of epochs and tried changing model type (attempted Logistic regression and Sequential models). Lastly, I attempted to try different activation functions (ReLU, sigmoid, and leaky ReLU), as well as changing the number of hidden layers and neurons. 
  
