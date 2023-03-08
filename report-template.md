# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### BELLO ISMAHEEL

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When I used the Sagemaker Studio the part "| tail -n +1 | head -n 6" worked well and submitted but didn't work on my local computer,so I had to remove the part from the submission.
### What was the top ranked model that performed?
The model KNeighborsDist_BAG_L1 performed better with a score value of -84.146423, when i used XGBOOST, the model XGBoost_BAG_L2 performs better with a score value of -210.950986, then for GBM algorithm LightGBM_BAG_L2 performs better with score value -167.987094.
## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
From the exploratory i noticed that some columns(windspeed,casual,registered,count) were negatively skewed, others like month,day has more than one mode.
I added additional features by separating datetime into Day and Month.

### How much better did your model preform after adding additional features and why do you think that is?
Although, I run the code severally, and most often the model perform better whenever I add new features.
## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After changing some columns to category, I tried using multiclass as my evaluation metrics and I can see that it performs better than when I used regression.

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time interpreting the models.
### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|-84.146423|-84.146423|0.012451|1.84672|
|add_features|-84.146423|-84.146423|0.012451|1.84672|
|hpo|-101.588176|-101.588176|0.004646|2.35363|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](model_test_score.png)

## Summary
The data was first trained without adding any features to it,then to future see if the model will perform if more features are being added, I added two more features to the dataset and it performs better,individual algorithm type was also used during the fitting. I noticed that adding more parameters while fitting the model may help the model perform better.