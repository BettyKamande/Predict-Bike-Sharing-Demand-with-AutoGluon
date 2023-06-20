# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### BETTY KAMANDE

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: 1. We needed to set the predictor's parameters: a) The evaluation metric = root mean squared error b) Time limit = 600(seconds) c) Presets = best quality
      2. We needed to set the predictions > 0 or have the negative values >= 0

### What was the top ranked model that performed?
TODO: The top ranked model was WeightedEnsemble_L3. It had the least root mean squared error of 53.146698 in the initial model training run. When additional features were added it came down to 30.094684. However, after hyper parameter tuning, the model score increased to 36.792012

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: We generally have 4 seasons. Temp and atemp generally have a normal distribution. The count column is positively skewed. More data points are concentrated on the left hand side. This
means the mean is greater than the median and the mode is less than the median and the mean. 
      I added additional features from the datetime column and feature engineered: year, month, dayofweek, hour, minute and seconds using the pandas library.  

### How much better did your model preform after adding additional features and why do you think that is?
TODO: The initial score was 1.78902 and it improved to 0.68269. This means the root mean squared error reduced hence the model was performing better after adding additional features.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: The new_feature score, 0.68269, was reduced to 0.48842 . It got better by 0.19427 . The kaggle score reduced but the model score increased. 

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: I would definitely play around with the hyper parameters, adjusting them to see how best they score or can improve the model. This is by setting the best combinations to optimize the model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|hpo4|hpo5|score|
|--|--|--|--|--|
|initial|eval_metric = 'root_mean_squared_error'|time_limit = 600|presets = 'best_quality'|None|None|1.78902|
|add_features|eval_metric = 'root_mean_squared_error'|time_limit = 600|presets = 'best_quality'|None|None|0.68269|
|hpo|eval_metric = 'root_mean_squared_error'|time_limit = 600|presets = 'best_quality'|num_bag_sets = 5|num_stack_levels = 3|0.48842|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](nd009t-c1-intro-to-ml-project-starter/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](nd009t-c1-intro-to-ml-project-starter/model_test_score.png)

## Summary
TODO: It is important to do both feature engineering and hyper parameter tuning to increase the performance of a model. However, not always does hyper parameter improve a model. We need to find the best set of combinations of hyper parameters to optimize the model otherwise occurrences like overfitting may happen.
