A-Source Data:
  to be downloaded from: 
  https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
  
  
P.S.  Assuming that the data is already Present in an uncompressed format and raw / intact

B- R-Code Explanation: 
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

C- Variables:
  >  x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.
  >  x_data, y_data and subject_data merge the previous datasets to further analysis.
  features contains the correct names for the x_data dataset, which are applied to the column names stored in