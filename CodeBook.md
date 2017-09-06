## Code Book

### Description of the variables and their transformations:
1. dataset_path - path to UCI HAR Dataset folder
2. train_subj - content of subject_train.txt
3. test_subj - content of subject_test.txt
4. train_activities - content of y_train.txt
5. test_activities - content of y_test.txt
6. dt_train - content of X_train.txt
7. dt_test - content of X_test.txt
8. dt_subject - train_subj and test_subj data merged with rbind. Column names are set to 'V1' and 'subject'
9. dt_activity - train_activity and test_activity data merged with rbind. Columnt names are set to 'V1' and 'activity_index'
10. dt - dt_train and dt_test data merged with rbind
11. dt_subject - dt_subject and dt_activity data merged with cbind
12. dt - dt_subject and dt data merged with cbind
13. features - content of features.txt. Column names are set to 'feature_index' and 'feature_name'
14. features is modified to remove all rows not containing mean or standart derivation measurements
15. features is modified to include 'feature_code' column corresponding to column names in dt
16. dt is subset to include only columns with mean and standart derivation measurements according to 'feature_code' in features
17. activity_names - content of activity_labels.txt that includes descriptive names for activity types
18. dt is merged with activity_names by activity_index
19. dt is melted into long and narrow representation by 'feature_code'
20. dt is merged with features by 'feature_code'
21. dt is modified to include activity and feature as factors with respective names
22. new_names - a vector containing column names to be left in a final dataset
23. dt is modified to remove redundant columns using new_names vector
24. tidy_dataset - final dataset created from dt and containing average values of many measurements of the same subject, activity and feature together with a number of measurements done for each combination of variables

### Final tidy dataset columns description:

1. subject - a number from 1 to 30 assign to every distinct subject of the experiment
2. activity - a type of activity undertaken by the subject during the measurements
3. feature - a feature being measured
4. count - a number of times that a certain feature was measured for a given subject and activity |
5. value - mean of the results of the measurements done for same feature, subject and activity