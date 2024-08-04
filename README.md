<img src="https://github.com/Gavin-Wda/London-Rain/blob/main/360_F_87682101_rOWDuYaxPFAukcJP0oS7CIy1tiDTmE2U.jpg" alt="London Banner">

# London-Rain
This repository, being my first project, uses London weather data from 1979 to 2021 in order to predict the presence of rain on a given day. 


Overview

The goal of this project was to create two different tree-based models to predict if it would rain or not in London. The data used was provided by the European Climate Assessment (ECA), covering weather data from 1979 to 2021, recorded by a weather station near Heathrow Airport. The final model was an XGBoost Classifier with a 74.58% Accuracy, 74.65% AUC, and 73.59% f1 score on unseen test data. Based on the model, air pressure, max temperature, and sun hours were the most influential features in determining rain or no rain. 

https://www.ecad.eu/dailydata/index.php

Understanding / context 

London is notorious for receiving rain on a regular basis. According to visitlondon.com, London sees rain 11-15 days per month on average, with August and November being the most prominent. Thus, if one would want to dress appropriately each day, it would be imperative to understand what weather factors are associated with rainy days within the city. As for my trip in August, I do not dress for rain if I don’t have to, given that it is the city’s hottest month. 

Data Understanding 

The London Weather Measurements data, from 1979 to 2021, comes from the European Climate Assessment & Dataset Project. The set contains entries for each day, creating 15341 entries, with 10 features including date, cloud cover, pressure, mean temperature, and global radiation. In preparation for the model a boolean column representing if it rained was added. It was found that this outcome variable was fairly balanced at 48.12% (rain) and 52.88% (no rain). Furthermore, as the snow column had many missing entries and only 140 days (0.913%) of snow presence, it was removed. Any categorical fields were replaced with dummies. 

Model and Evaluation 

In building the XGBoost model a GridSearch was used over a set of parameters, including max_depth, min_child_weight, learning_rate, and n_estimators. The best parameters found were 200 boosting rounds, max depth of four, minimum child weight of four, and a learning rate of 0.05. It was found that the top three most important factors indicating the presence of rain or not on a given day were pressure, max temperature, and sun hours. The model, on test data, received an AOC score of 74.65% and accuracy score of 74.58%. 

<img src="https://github.com/Gavin-Wda/London-Rain/blob/main/feature%20importance.png" alt="XGBoost Feature Importance Chart">

Conclusion 

This model can be useful in determining the presence of rain with fairly good results, meaning it can be a helpful tool for me when I go on my trip in August! Going forward, it may be beneficial to do some feature engineering like day-temp range and potentially introduce other weather related metrics such as wind speed and humidity to improve scores. I also believe that though this model is very specific to my scenario, I believe that this data could be paired with other date specific datasets like vehicle accidents or tube use to generate more applicable predictive models. 
