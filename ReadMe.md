## Preparing the data project

### How the run_analysis.R script works

`run_analysis.R` is designed to work with UCI HAR dataset.
The dataset can be downloaded at: [link to the dataset](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
The description of the original dataset is provided at: [description of the dataset](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

In order for script to work the dataset should be unzipped and placed at the same directory as the script.
Dataset should be placed in a folder "UCI HAR Dataset" with the following structure:
```
activity_labels.txt
features.txt
features_info.txt
README.txt
test/Inertial Signals/body_acc_x_test.txt
test/Inertial Signals/body_acc_y_test.txt
test/Inertial Signals/body_acc_z_test.txt
test/Inertial Signals/body_gyro_x_test.txt
test/Inertial Signals/body_gyro_y_test.txt
test/Inertial Signals/body_gyro_z_test.txt
test/Inertial Signals/total_acc_x_test.txt
test/Inertial Signals/total_acc_y_test.txt
test/Inertial Signals/total_acc_z_test.txt
test/subject_test.txt
test/X_test.txt
test/y_test.txt
train/Inertial Signals/body_acc_x_train.txt
train/Inertial Signals/body_acc_y_train.txt
train/Inertial Signals/body_acc_z_train.txt
train/Inertial Signals/body_gyro_x_train.txt
train/Inertial Signals/body_gyro_y_train.txt
train/Inertial Signals/body_gyro_z_train.txt
train/Inertial Signals/total_acc_x_train.txt
train/Inertial Signals/total_acc_y_train.txt
train/Inertial Signals/total_acc_z_train.txt
train/subject_train.txt
train/X_train.txt
train/y_train.txt
```

For the purpose of this project files in 'Inertial Signals' folders are not used.
The list of files that are accessed by the script:
```
activity_labels.txt
features.txt
test/subject_test.txt
test/X_test.txt
test/y_test.txt
train/subject_train.txt
train/X_train.txt
train/y_train.txt
```

The scripts does the following:
1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

### Steps to reproduce the project
1. Place an unzipped folder with the dataset in the same directory as the script
2. Use R console to set working directory to the directory with the script and the dataset using `setwd()` command
3. Run the R script `run_analysis.R`
4. As a result new file `tidy_dataset.txt` is created in the same directory

### Dataset codebook
Final tidy dataset columns description:

1. subject - a number from 1 to 30 assign to every distinct subject of the experiment
2. activity - a type of activity undertaken by the subject during the measurements
3. feature - a feature being measured
4. count - a number of times that a certain feature was measured for a given subject and activity |
5. value - mean of the results of the measurements done for same feature, subject and activity