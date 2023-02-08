# Course-3-Project

This codebook was created to explain the variables, and include any other information relevant to the reader. 

Information regarding the Data set 
30 volunteers did 6 activities while wearing a smartphone on their waists. These activities were WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING. 

I created the script "run_analysis.R" -- 

Provided is the following:
Triaxial acceleration from the accelerometer along with the estimated body acceleration.
Triaxial Angular velocity.
A vector with time and frequency domain variables.
Activity label.
An label for the subject who enacted the experiment.
The dataset includes these files:
'README.txt'

'features_info.txt': Shows information about the variables used on the feature vector.

'features.txt': List of all features

'activity_labels.txt': Links the class labels with their activity name

'train/X_train.txt': Training set

'train/y_train.txt': Training labels

'test/X_test.txt': Test set

'test/y_test.txt': Test labels

The following files are available for the train and test data.

'train/subject_train.txt'

'train/Inertial Signals/total_acc_x_train.txt'

'train/Inertial Signals/body_acc_x_train.txt'

'train/Inertial Signals/body_gyro_x_train.txt'

Merged the training and the test sets to create one data set.
Extracted the measurements on the mean and standard deviation for each measurement.
Used descriptive names to name the activities in the data set
Labeled the data set with variable names.
Created a tidy data set with the average of each variable for each activity and each subject.

After installation and getting data, to merge the training and test set, I first filtered out the mean and standard deviation, first with grep, and to do that I loaded the activity labels and features text file, getting patterns which matches the words "mean", and "str". I also created a measurements variable which contained the variable names to be labelled on the test and training data set, and tidying the name with gsub. Then with the column indexes containing mean and std, the train and test set files can be loaded. I also renamed the variables using the setnames() functions. After than both the train and test file could be merged with rbind.

After creating a merged data set, I created a new data set with the average of each variable for each activity and each subject. To do that I first had to convert the variables in the Activity and SubjectNo. columns into factors. Then I utilized the reshape library to melt and cast the variables, in order to get the mean. Lastly, I wrote the tidy and clean dataset into a new text file.

Here are the descriptive variable names:
"t" = "Time"
"f" = "Frequency"
"Acc" = "Accelerometer"
"Gyro" = "Gyroscope"
"Mag" = "Magnitude"
"BodyBody" = "Body"
"()" = ""
