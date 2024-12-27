# Goal of the hackthon
The goal is to build an AI model that can predict the watertable/ground water levels of french piezometric stations, with a focus on the summer months. To build this model, you were given a data set of +3 million lines, more than 100
columns about piezometric/watertable, weather, hydrology, water withdrawal and social-economic data.

# Dataset 
The full dataset contains over 3 million rows with 136 columns. It was split into a train/test set.
Train set (X_train_Hi5.csv): The dataset has around 2 800 000 rows. It contains data between 2020 and 2023, excluding the summer months (june, july, august, september) of 2022 and 2023.  
Test set (X_test_Hi5.csv): The dataset contains has around 600 000 rows. It contains data for the 2022 and 2023 summer months (june, july, august, september).Test submission example (y_test_submission_example_Hi5.csv): Please follow this example to submit results to the leaderboard. The "row_index" variable is a unique identifier of each row, to match the values
The target variable to predict is piezo_groundwater_level_category.

--

