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

