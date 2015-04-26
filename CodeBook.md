# Workflow

The script `run_analysis.R`performs the 5 steps described in the course project's definition.

* 1: all the similar data is merged using the `rbind()` function. By similar, we address those files having the same number of columns and referring to the same entities.
* 2: only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
* 3: Activity data is addressed with values 1:6, activity names and IDs from `activity_labels.txt` are used and are substituted in the dataset.
* 4: On the whole dataset, columns with vague column names are corrected.
* 5: A new dataset is generated with all the average measures for each subject and activity type i.e. 6 activities x 30 subjects   = 180 rows. The output file , `averages_data.txt` , is uploaded to this repository.

# Variables

* 1: `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* 2: `x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
* 3: `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`, a numeric vector used to extract the desired data.
* 4: same is done with activity names through the `activities` variable.
* 5: `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* 6: `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans() .

