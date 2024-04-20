# Report: Predict Bike Sharing Demand with AutoGluon 

#### Bhagya sri Uddandam

## Initial Training

### What was the top ranked model that performed?

The remarkable WeightedEnsemble_L3 was the model that performed the best out of all the ones I trained. Its resilience and capacity to integrate knowledge from several models turned out to be crucial in attaining increased prediction precision.


## Exploratory data analysis and feature creation

### What did the exploratory analysis find and how did you add additional features?

After conducting extensive exploratory data analysis, I noticed a significant link between the "temp" and "atemp" variables. As a result, I took the deliberate choice to remove "atemp" from the feature set. Furthermore, I saw that the recorded "datetime" information was hourly, so I creatively separated day, month, year, and hour as distinct aspects. I also used categorical data type conversions for specific variables to improve the model's knowledge of the data.

### How much better did your model preform after adding additional features and why do you think that is?

The incorporation of new features led to a significant boost in the model's performance. The error rate decreased significantly, showing that the model got a better knowledge of the underlying patterns and dynamics in the dataset. By expanding the feature set, the model was able to extract more significant insights, resulting in higher prediction accuracy.

## Hyper parameter tuning



### Create a table with the models you ran, the hyperparameters modified, and the kaggle score

|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_values|default_values|default_values|1.80|
|add_features|default_values|default_values|default_values|0.72|
|hpo|GBM: num_leaves: lower=26, upper=66|XGB: max_depth lower=5, upper=9|refit_full='best'|0.49|

### Create a line plot showing the top model score for the three (or more) training runs during the project

![model_train_score.png](img/plot1.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project

![model_test_score.png](img/plot2.png)

## Summary

In summary, I used the first lesson's courses to my project. I used AutoGluon to train a model that predicts how many bikes would be leased in a given hour. I originally submitted the proposal with no analysis or feature engineering. The model performed miserably. I was able to enhance the model by adding new features and adjusting the hyperparameters. I managed to minimize the error from 1.80 to 0.49.
