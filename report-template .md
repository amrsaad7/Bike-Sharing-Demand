# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Amr Elsayed

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
The first thing I realized is that AutoGluan can automatically recognize the task since I didn't provide the problem type as a parameter but still was able to know it was a regression problem. Regarding the prediction scores, I didn't have any negative scores, but still added a piece of code to set negative numbers to 0 as it was one of the steps.

### What was the top ranked model that performed?
Top ranked model: WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The EDA showed how each feature is relative to the data. I broke down the datetime feature into four new features: year, month, day, and hour. Moreover, I added category type to the season and weather features so models can recognize them.

### How much better did your model preform after adding additional features and why do you think that is?
Adding more features increased the performance of models significantly. It improved the best model WeightedEnsemble_L3 by 53%.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
It performed significantly better than the initial one, but not as well as the previous one when I added new features. Maybe if I fine tuned the parameters more, I would get better results.

### If you were given more time with this dataset, where do you think you would spend more time?
I would do more EDA to understand the data more. Also, I would try to play with the hyperparameters more and fine tune them to get the best result possible. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_params|default_params|default_params|1.81237|
|add_features|default_params|default_params|default_params|0.68065|
|hpo|NN|num_trials|GBM|0.47746|

### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.


![model_test_score.png](img/model_test_score.png)

## Summary
The project was mainly about predicting demand using Autogluan. I trained the data three times throughout this project. At first, I trained the original data and got decent results, but not the best. The second time, I did some EDA on the data and added some features, then I trained the data again and the results improved significantly after applying EDA. Lastly, I did optimize the hyperparameters to try to get even better results. The results were better than the initial ones, but unfortunately not better than the one I did after EDA.  
