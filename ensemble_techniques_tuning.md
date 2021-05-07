# Ensemble Techniques Hyperparameter Tuning
The hyper-parameter settings of the final classifiers are optimized for
precision using
[GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html).
The parameter grid for each technique can be found below, which was tested, can
be found in the online appendix\dd{To be added}. The hyperparameters, which are
not featured in the tables, were left at their default values provided by
scikit-learn. We set up the weights of the base models for Voting to either
fully include or exclude each base model in the prediction. This step allows
examining which models complement each other and, following, which combination
of models results in the best predictions. When using Stacking, we employed all
previously described base models as final estimators.

***

## Voting Classifier

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.VotingClassifier.html

| Hyper-Parameter |          Values           |                                        Description |
| --------------- | :-----------------------: | -------------------------------------------------: |
| weights | [[0, 0, 0, 1], [0, 0, 1, 0], <br /> [0, 0, 1, 1], [0, 1, 0, 0], <br /> [0, 1, 0, 1], [0, 1, 1, 0], <br /> [0, 1, 1, 1], [1, 0, 0, 0], <br /> [1, 0, 0, 1], [1, 0, 1, 0], <br /> [1, 0, 1, 1], [1, 1, 0, 0], <br /> [1, 1, 0, 1], [1, 1, 1, 0], <br /> [1, 1, 1, 1]] | The sequence of weights of<br /> (i) the occurrences of predicted class labels (hard voting);<br /> (ii) the class probabilities before averaging (soft voting).|
| voting | ['soft'] |  Predicts the class label based on the argmax <br /> of the sums of the predicted probabilities.|

***

## Stacking Classifier

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.StackingClassifier.html

| Hyper-Parameter |          Values           |                                                                                               Description |
| --------------- | :-----------------------: | --------------------------------------------------------------------------------------------------------: |
| final_estimator | [DecisionTreeClassifier(), SVC(), RandomForestClassifier(), LogisticRegression(), GaussianNB()] | The classifier which will be used to combine the base estimators.|
| stack_method | ['precict\_proba'] | The methods called for each base estimator. |
