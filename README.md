# datasciencecoursera
run_Analysis.R readMe

In the run_Analysis.R file, at first the training data set is created 
by reading the table values from the path of the file that was specified by taking the X_train and Y_train .txt files as well as the subject_train.txt
and assigning them to the corresponding xtrain and ytrain and subject_train variables that were defined. 

In the same way the testing data was created as well.

Then the features data was read from the features.txt file. 

Following that Creating Sanity and Column Values to the Train Data and Creating Sanity and column values to the test data was done.

Then Merging the train and test data which is an  important outcome of the project was done.

Then creation of the main data table and merging  of both  the table was done.

Next step was reading all the values that were available.

We needed to get a subset of all the mean and standards and the corresponding activityID and subjectID. So this was done by using grepl 
and the pipeline operation. 

A subset was created to get the required dataset.

Then the new tidy data set was created and ordered according the activityID and subjectID.

The last step was to write the output which is the tidy data set to a text file which was done using write.table 

