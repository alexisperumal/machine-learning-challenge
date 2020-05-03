## machine-learning-challenge
UCSD Data Science Bootcamp - ML Project

### Objective
• Analyze the provided exoplanet database and develop a classifier model to identify potential exoplanets into one of three categories: Candidate, False Positive, and Confirmed.

### Approach
• Separate the dataset into a training and test sets, select features, run models on scaled data, do hyperparameter optimization and further feature engineering, then propose a model.

### Key Files
• Model_x_compare.ipynb - Jupyter Notebook running several models, generally with default parameters, on the groomed dataset. https://github.com/alexisperumal/machine-learning-challenge/blob/master/model_x_compare.ipynb

• Model_4_random_forest.ipynb - Optimal model of 4 tried, random forest, with tuned parameters. https://github.com/alexisperumal/machine-learning-challenge/blob/master/model_4_random_forest.ipynb

• alexis-random-forest.sav - model file of the tuned random forest. https://github.com/alexisperumal/machine-learning-challenge/blob/master/alexis-random-forest.sav

### Model Building and Analysis
3 categorical outcomes (Candidate, False Positive, or Confirmed) led to the usage of classifier models, starting with the basic Logistical Regression, implemented in model_1.ipynb.

#### Logistical Regression Model

Without meaningful domain knowledge on the 40 potential independent variables (features), I eliminated the error columns but proceededed with the remaining. The split and scaled dataset consisted of 5,243 training set values and 1,748 test set values. Results were 81.9% for thetraining set and 83.1% for the test set. Hyperparamter tuning of the C and penalty parameters improved this to 82.1% correctness for the training set.


### Additional Models

In addition to logistic regression, several other classifier models were attempted in the model_x_compare.ipynb file. These include the following model with the indicated test set correctness Logistic Regressionm (83.1%), Random Forest (91.1%), K Nearest Neighbors (81.1%), Support Vector Classification (84.1%), and Stochastic Gradient Descent (81.9%). Those results were with default parameters.

Individual models were further tuned in individual notebook files.

The best overall result was Random Forest with 91.1% accuracy on the test set using 13 featues. Feature tuning was looked at using both feature importances resulting from the GridSearch analysis and also Recursive Feature Elimination. With RFE, the top 13 features were selected. (Natural breakpoints existed at 7 features and 13, with dimishing returns beyond 13.)

Overall, Random Forest wroked well for this dataset test set despite the 1.0 training data score possibly suggesting some amount of over fitting.



