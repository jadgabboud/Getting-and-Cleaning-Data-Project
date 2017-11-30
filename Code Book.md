# A-Source Data:

  to be downloaded from: 
  https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
  
  
P.S.  Assuming that the data is already Present in an uncompressed format and raw / intact

# B- R-Code Explanation: 

  ## Introduction
The script `run_analysis.R`performs the 5 steps described in the course project's definition.
* First, all the similar data is merged using the `rbind()` function. By similar, we address those files having the same number of columns and referring to the same entities.
* Then, only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* On the whole dataset, those columns with vague column names are corrected.
* Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `averages_data.txt`, and uploaded to this repository.

File with R code "run_analysis.R" perform 5 following steps (in accordance assigned task of course work):
1. Merging the training and the test sets to create one data set.
  1.1 Reading files
  1.1.1 Reading trainings tables
  1.1.2 Reading testing tables
  1.1.3 Reading feature vector
  1.1.4 Reading activity labels
  1.2 Assigning column names
  1.3 Merging all data in one set
2. Extracting only the measurements on the mean and standard deviation for each measurement
  2.1 Reading column names
  2.2 Create vector for defining ID, mean and standard deviation
  2.3 Making necessary subset from setAllInOne
3. Using descriptive activity names to name the activities in the data set
4. Appropriately labeling the data set with descriptive variable names
5. Creating a second, independent tidy data set with the average of each variable for each activity and each subject
  5.1 Making second tidy data set
  5.2 Writing second tidy data set in txt file
PS..The code takes for granted all the data is present in the same folder, un-compressed and without names altered.

# C - Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.


