## machine-learning-challenge
UCSD Data Science Bootcamp - ML Project

### Objective
• Analyze the provided exoplanet database and develop a classifier model to identify potential exoplanets into one of three categories: Candidate, False Positive, and Confirmed.

### Approach
• Separate the dataset into a training and test sets, select features, run models on scaled data, do hyperparameter optimization and further feature engineering, then propose a model.

### Key Files
• Model_x_compare.ipynb - Jupyter Notebook running several models, generally with default parameters, on the groomed dataset. https://github.com/alexisperumal/machine-learning-challenge/blob/master/model_x_compare.ipynb

• Model_4_random_forest.ipynb - Optimal model of 4 tried, random forest, with tuned parameters. https://github.com/alexisperumal/machine-learning-challenge/blob/master/model_4_random_forest.ipynb

• Model_4_random_forest-OHE.ipynb - Variant of Model 4 with one hot encoding type label encoding of the y categorical dependent variable. https://github.com/alexisperumal/machine-learning-challenge/blob/master/model_4_random_forest-OHE.ipynb

• alexis-random-forest.sav - model file of the tuned random forest. https://github.com/alexisperumal/machine-learning-challenge/blob/master/alexis-random-forest.sav

• alexis-random-forest-OHE.sav - model file of the OHE variant of random forest. https://github.com/alexisperumal/machine-learning-challenge/blob/master/alexis-random-forest-OHE.sav

### Model Building and Analysis
3 categorical outcomes (Candidate, False Positive, or Confirmed) led to the usage of classifier models, starting with the basic Logistical Regression, implemented in model_1.ipynb.

#### Logistical Regression Model

Without meaningful domain knowledge on the 40 potential independent variables (features), I eliminated the error columns but proceededed with the remaining. The split and scaled dataset consisted of 5,243 training set values and 1,748 test set values. Results were 81.9% for thetraining set and 83.1% for the test set. Hyperparamter tuning of the C and penalty parameters improved this to 82.1% correctness for the training set.


#### Additional Models

In addition to logistic regression, several other classifier models were attempted in the model_x_compare.ipynb file. These include the following model with the indicated test set correctness Logistic Regressionm (83.1%), Random Forest (91.1%), K Nearest Neighbors (81.1%), Support Vector Classification (84.1%), and Stochastic Gradient Descent (81.9%). Those results were with default parameters.

Individual models were further tuned in individual notebook files.

The best overall result was Random Forest with 91.1% accuracy on the test set using 13 featues. Feature tuning was looked at using both feature importances resulting from the GridSearch analysis and also Recursive Feature Elimination. With RFE, the top 13 features were selected. (Natural breakpoints existed at 7 features and 13, with dimishing returns beyond 13.) The .sav file was saved with verification of the idential results when the model was loaded from the .sav file.

Overall, Random Forest wroked well for this dataset test set despite the 1.0 training data score possibly suggesting some amount of over fitting.

Lastly, there was a question on if encoding of the y categorical variable, one hot encoding style, would impact the model result or performance. This was implemented in a variant notebook. The outcomes were identical although the processing time was a bit slower - however, we don't know if the slowdown was caused by a different state of the computer when the variant was run.





