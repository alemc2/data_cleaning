data_cleaning
=============

Repo for getting and cleaning data course on coursera

run_analysis.R
--------------
Forms and stores a tidy summary of the given data. The variables from the script and the transforms applied are mentioned in detail in CodeBook.md
This script performs the following steps:
* Forms a data frame containing features and results for each subject in the training set.
* Forms a data frame containing features and results for each subject in the test set
* Combines these two into a single data frame.
* Sets column names and activity labels.
* Extracts from it a data frame containing mean and standard deviation features for each subject.
* Cleans up column names to be more readable.
* Forms a tidy summary from the new data frame containing averages of mean and standard deviation features for each subject during each activity.

###Results
* `data` - Contains the combined data of the training and test sets.
* `meansDevs` - Contains only mean and standard deviation columns for each subject.
* `dataSummary` - Contains averages of mean and standard deviation values for each combination of activity and subject. It is written to `data_summary.txt` in the given data folder.

###Assumptions
* The provided data must be unzipped into a data directory the working directory before running this script. That is, `data/UCI HAR Dataset` must be a subdirectory of the current directory.
* Library `reshape2` is required.
* When extracting mean and standard deviation measurements, only columns with names containing `-mean()` and `-std()` are used. Those containing `-meanFreq()` are ignored.
* The tidy data set is created from means/deviations data set and not from the overall data set.
* The final result contains average values for each subject while performing each activity.
