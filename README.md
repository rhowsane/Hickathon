# Goal of the hackthon 2024💦
The goal is to build an AI model that can predict the watertable/ground water levels of french piezometric stations, with a focus on the summer months. To build this model, you were given a data set of +3 million lines, more than 100
columns about piezometric/watertable, weather, hydrology, water withdrawal and social-economic data.

# Dataset 
The full dataset contains over 3 million rows with 136 columns. It was split into a train/test set.    
`Train set (X_train_Hi5.csv):` The dataset has around 2 800 000 rows. It contains data between 2020 and 2023, excluding the summer months (june, july, august, september) of 2022 and 2023.    
`Test set (X_test_Hi5.csv):` The dataset contains has around 600 000 rows. It contains data for the 2022 and 2023 summer months (june, july, august, september).  
The "row_index" variable is a unique identifier of each row, to match the values.  
The target variable to predict is piezo_groundwater_level_category.

---

# Initial step

As reading the file X_train.csv with pandas exceeded the RAM memory of my computer, I used the linux command below
to keep the header, shuffle the rest of the dataset and take 100,000 lines.
```
(head -n 1 X_train.csv && tail -n +2 X_train.csv | shuf -n 100000) > sampled_file.csv
```

***Obs:*** The train and test datasets exceed git supporting limit. That's why they are not in this repository.  

# Development  

Firstly, I checked the if the prediction labels were unbalanced.  

Secondly, I started the preprocessing: 
- the columns ending by _INSEE of type object were converted into numeric, 
- I extracted the year and month of the dates of meteo and piezo, and
- normalized the `piezo_station_department_code`, for instance, so that 3 will be converted to 03.

Then, I splitted the dataset into train and test.

# Conclusions
Concerning the modelling part, I adopted a first dummy model as baseline, giving 20% as score prediction on the test set.  
The second model was a LightGBM with standards hyperparameters, giving a 47% on the validation dataset of the leaderboard.  
And the final strategy was to automatize the hyperparameter tunning of the model using FLAML. With it, the final score was of 54%. When trained on the hole dataset with a computer with more RAM, it produced a score of 57%.
The most important features can be seen on the Feature importance chart.



