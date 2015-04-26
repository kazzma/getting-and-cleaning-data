# Code Summary

The script `run_analysis.R`performs the 5 steps described in the course project's definition.

-First, all the similar data is merged using `rbind()`. By similar, we address those files having the same number of columns and referring to the same entities.
-Only the columns with the mean and standard deviation measures are being fetched from the dataset and given the relevant names, taken from `features.txt`.
-We take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
-The columns with the undescriptive column names are corrected.
-We create a new dataset with all the average measures for each subject and activity type .The output file is called `averages.txt`, and uploaded to this repository.



# Variables Description

-`x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
-`x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
-`features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`, a numeric vector used to extract the desired data.
-A similar approach is taken with activity names through the `activities` variable.
-`all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
-Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.
