Original data source: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
Original description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Datasets:

The following text files: 

'README.txt': Information on the data set.

'features_info.txt': Information on the variables used.

'features.txt': List of features.

'activity_labels.txt': Class labels / activity name.

'train/X_train.txt': Training set.

'train/y_train.txt': Training labels.

'test/X_test.txt': Test set.

'test/y_test.txt': Test labels.

The following test files are available for the training and test data.

'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30.

'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis.

'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.

'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.


The following transformations are performed on the data:

1) Merges the training and the test sets to create one data set.
2) Extracts only the measurements on the mean and standard deviation for each measurement.
3) Uses descriptive activity names to name the activities in the data set
4) Appropriately labels the data set with descriptive activity names.
5) Creates a second, independent tidy data set with the average of each variable for each activity and each subject.


The code run_analysis.r runs the following steps to achieve this:

1) Gets the current directory and sets the working directory to "~/Documents/Data_Science_Specialization_Coursera/Getting_and_cleaning_data/"

2) Uses read.table to read the entries of the following text files: features.txt, X_train.txt, Y_train.txt, subject_train.txt, X_test.txt, Y_test.txt, subject_test.txt, activity_labels.txt.

3) Uses factor and colnames to assign descriptive activity names.

4) Uses cbind and rbind to merge the data. This is written out with write.table.

5) Uses the grep function to find and extract the means and standard deviations.

6) Uses ddply (in the plyr library) to apply the function average to the subject and activity measurements. Again writes out result with write.table.
