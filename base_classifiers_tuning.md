# Base Classifiers Hyperparameter Tuning
A random search over the hyperparameter space is applied using scikit-learn's
[RandomizedSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html).
e run the randomized search for 200 iterations per machine learning technique,
embedding, and combination of feature pre-processings steps. This algorithm
randomly samples the hyperparameter from the parameter distributions described
in the following tables, those not specified are kept to their default value
provided by scikit-learn.

***
## Decision Tree

https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html

https://docs.scipy.org/doc/scipy/reference/stats.html

| Hyper-Parameter    |           Values            |                                                         Description |
| ------------------ | :-------------------------: | ------------------------------------------------------------------: |
| max. depth         | scipy.stats.randint(10,100) |                                      The maximum depth of the tree. |
| max. features      |  ['auto', 'sqrt', 'log2']   | The number of features to consider when looking for the best split. |
| min. samples split |  scipy.stats.randint(1, 9)  |   The minimum number of samples required to split an internal node. |
| criterion          |     ['gini', 'entropy']     |                     The function to measure the quality of a split. |

***

## Random Forest

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html

https://docs.scipy.org/doc/scipy/reference/stats.html

| Hyper-Parameter    |             Values             |                                              Description |
| ------------------ | :----------------------------: | -------------------------------------------------------: |
| bootstrap          |         [True, False]          |  Whether bootstrap samples are used when building trees. |
| max. depth         |  scipy.stats.randint(10,100)   |                           The maximum depth of the tree. |
| max. features      |    ['auto', 'sqrt', 'log2']    |               The number of features for the best split. |
| min. samples split |   scipy.stats.randint(1, 9)    | The minimum number of samples to split an internal node. |
| criterion          |      ['gini', 'entropy']       |          The function to measure the quality of a split. |
| nr. of estimators  | scipy.stats.randint(100, 1500) |                       The number of trees in the forest. |

***

## Adaboost

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostClassifier.html

https://docs.scipy.org/doc/scipy/reference/stats.html

| Hyper-Parameter   |             Values             |                                                Description |
| ----------------- | :----------------------------: | ---------------------------------------------------------: |
| n_estimators      | scipy.stats.randint(100, 1500) |                  The number of boosting stages to perform. |

***

## Gradient Boosting

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html

https://docs.scipy.org/doc/scipy/reference/stats.html

| Hyper-Parameter   |             Values             |                                                Description |
| ----------------- | :----------------------------: | ---------------------------------------------------------: |
| max_depth         |  scipy.stats.randint(10,100)   | The maximum depth of the individual regression estimators. |
| max_features      |    ['auto', 'sqrt', 'log2']    |                 The number of features for the best split. |
| min_samples_split |   scipy.stats.randint(1, 9)    |   The minimum number of samples to split an internal node. |
| n_estimators      | scipy.stats.randint(100, 1500) |                  The number of boosting stages to perform. |

***

## Support Vector Machine

https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html

https://docs.scipy.org/doc/scipy/reference/stats.html

| Hyper-Parameter |           Values            |                   Description |
| --------------- | :-------------------------: | ----------------------------: |
| C               | scipy.stats.uniform(2, 10)  | The regularization parameter. |
| gamma           | scipy.stats.uniform(0.1, 1) |       The kernel coefficient. |

***

## Logistic Regression

https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html

https://numpy.org

| Hyper-Parameter |          Values           |                                        Description |
| --------------- | :-----------------------: | -------------------------------------------------: |
| C               | numpy.logspace(-4, 4, 20) |            The inverse of regularization strength. |
| penalty         |       ['l1', 'l2']        | Used to specify the norm used in the penalization. |
| solver          |       ['liblinear']       |  The algorithm to use in the optimization problem. |

***

## Gaussian Naive Bayes

https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html

https://numpy.org

| Hyper-Parameter |          Values           |                                                                                               Description |
| --------------- | :-----------------------: | --------------------------------------------------------------------------------------------------------: |
| var_smoothing   | numpy.logspace(0,-9, 100) | The portion of the largest variance of all features <br /> that is added to variances for calculation stability. |