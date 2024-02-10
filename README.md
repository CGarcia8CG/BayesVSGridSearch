## GridSearch vs BayesianSearch

This is a comparison using a random forest model with 5 variables (X's) and a binary target (y)

Data is unbalanced 60% are class 0 and 40% are class 1 with 10,000 rows.

Training is 8000 rows with 5 CrossValidation, and using this param grid and the equivalent in BayesianSeach:

param_grid = {
    'n_estimators': [50, 100, 200],
    'max_depth': [None, 10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4]
}

Bayes
param_dist = {
    'n_estimators': (50, 200),
    'max_depth': (1, 30),
    'min_samples_split': (2, 10),
    'min_samples_leaf': (1, 4)
}

Results in terms of model performance with test set (Precision, Recall, etc.) is the same, but not the time it takes to train the models.
