# Neural_Network_Charity_Analysis
## Overview
- Use the Python TensorFlow library to create a binary classifier that is capable of predicting whether applicants will be successful if funded by the nonprofit foundation Alphabet Soup.


## Results
### <em>Data Preprocessing</em>
- What variable(s) are considered the target(s) for your model?
    - The target variable, or dependent variable, is the "IS_SUCCESSFUL" column. This variable is used to train the machine learning model.


- What variable(s) are considered to be the features for your model?
    - The features for the model include the input values, or the independent variables, which include all columns except that of the target variable and any dropped columns (EIN and NAME in this case).


- What variable(s) are neither targets nor features, and should be removed from the input data?
    - Variables that are neither targets nor features should be removed and do not add to the accuracy of the model. One such example would be variables with all unique values. We can drop outliers or utilize bucketing to address noisy data.


### <em>Compiling, Training, and Evaluating the Model</em>
- How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - 2 layers were used, 3 layers were tested but the addition of a third layer didn't contribute much to the improvement of the model.

    - relu activation function was chosen, as it is the most accurate for this model.

    - 200 neurons in layer1, and 90 neurons in layer2. As recommended, the first layer should contain at least double the amount of input features.

    - adam optimizer was chosen for it's gradient descent approach to ensure the algorithm will not get stuck on weaker classifying variables and features, and to enhance the performance of classification neural network.

    - binary crossentropy was used for the loss function, which is specifically designed to evaluate a binary classification model.

    - model was trained on 500 epochs, and was increased from 200 because the model showed improvement.


- Were you able to achieve the target model performance?
    - Target model performance was achieved after some configuration. Figures below show model accuracy started at 72.5% and increased to 76.1% after optimization.

    ![model accuracy](/images/accuracy.png "model accuracy")

    ![optimized accuracy](/images/accuracy_optimized.png "optimized accuracy")


- What steps did you take to try and increase model performance?
    - bin values in NAME column that are less than 50, reducing number of categorical values

    - Binned the ASK_AMT values

    - Added a third layer with 40 neurons, increased first layer to 200, second layer to 90

    - Increased epochs to 500


## Summary

- Overall, by increasing the accuracy from 72% to 76% we are able to correctly classify each of the points in the data 76% of the time. The analysis also shows there is a higher chance of an applicant being successful if the following applies:
    - NAME appears > 5 times
    - APPLICATION type is one of the following; T3-8, T10, T19
    - CLASSIFICATION type is one of the following; C1000, C2000, C3000, C1200, C2100

- The Random Forest model should be considered next to further improve performance. Due to the number of estimators and tree depth, this model is good for classificiation problems, is less influenced by outliers and is less likely to overfit the data. 
