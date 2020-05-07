---
title: "Codebook"
author: "Adittya"
date: "May 7, 2020"
output: pdf_document
---
Codebook

This is the codebook related to the R script run_analysis.R. It describes the output called tidy file.csv

Background Information
The goal of this script is to prepare tidy data from a larger dataset of accelerometer and gyroscope information from several Galaxy S smartphones.

A full description of the raw data is available at the site where the data was obtained: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Here are the data for the project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Raw Data Summary
30 subjects performed six different activities (walking, walking up stairs, walking down stairs, sitting, standing, and laying) while wearing their Samsung smartphone. The resulting accelerometer and gyrospcope data was then processed into 561 different time and frequency domain calculations. As of this project there were 10299 observations.

Script Output
We are only interested in the mean and standard deviation variables from the raw data.

The output of this script returns the mean of each of the below variables for each activity and each subject. i.e., these are the mean of the mean, or mean of the standard deviation of several variables for each subject and activity.

Variable description
The resulting variables are formatted as such:

subject - the first variable is the subject's number - no names are used, this is a unique identifier
activity - this variable is the activity the subject was performing at the time of the observation
The remaining variables are signals from:
Accelerometers tracking 3-axial linear acceleration (in the x, y, and z directions) measured in "G's" (gravity of earth -> 9.80665 m/s^2)
Gyroscopes tracking 3-axial angular velocity (in the x, y, and z directions) measured in rad/s
Every signal has a measured and calculated variable
every signal has a time domain component
A Fast Fourier Transform(FFT) provides a frequency domain calculation for some of the signals.
Body or Gravity indicates the nature of the movement (personal motion or motion induced by gravity)
X, Y, and Z indicate the cartesian direction of the variable.
jerk is the rate of change of acceleration
magnitude is the magnitude of the movement
The Format of the variables is: Time/Frequency - Body/Gravity - Accelerometer/Gyroscope - measure - Mean/StandardDev - direction

Transformations
Combine the TEST and TRAIN dataframes - of the true data. Called data
Combine the TEST and TRAIN dataframes - of the activities performed. Called activity
Combine the TEST and TRAIN dataframes - of the subjects being monitored. Called subjects
Read in the names of the features. Called features
Read in the names of the activities. Called activity_labels
Move the features to be the variable names in data
Combine the data with the subjects and activity. This is now a single dataframe.
Select only the mean and standard deviation measurements by grep'ing for mean() OR std()
Change the activities from a code to a description by merging the activity_lables into the data by using the activity_code as the primary key.
Update all of the variables so that they are human readible.
Add spaces.
Expand on the shortened terms or acronymns
Change the leading character to:
t = Time domain
f = Fast Fourier Transform (frequency domain)
Summary Data
Melt and recast the dataframe so that the average of each variable for each activity and each subject is calculated.

Create a text file with this data using write.table(), using row.name=FALSE, called tidy_summary_output.txt.txt