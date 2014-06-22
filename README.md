# coursera-uci-har

This script will combine the data in the [Human Activity Recognition Using Smartphones Data set](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) and output a new file **output.csv**, which will contain the average of all mean and standard deviation varabiles for each subject and activity.

Read the **CodeBook.md** file for more information.

## Usage

1. Please clone the repository and unzip the [UCI HAR Dataset](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) into a folder named **UCI HAR Dataset** within your R working directory.

2. Install the required reshape2 package with `install.packages("reshape2")`

3. Run the **run_analysis.R** script

## Script Analysis

The script performs the following functions on the raw data described above.

1. All training and test data is loaded in, as well as the column and activity labels
2. The train and test data are merged with their respective subjects before being combined with eachother
3. The columns are labeled using the data found in **features.txt**, however, these labels are first processed to remove any special characters known to cause issues with subsetting in R
4. The activity references are replaced with the labels loaded from **activity_labels.txt**
5. The entire dataset is subsetted to extract only features that are a function of mean or standard deviation
6. The subsetted data is then reshaped to take the average of each variable for a given subject and activity
7. The final tidy dataset is then exported as **output.csv** in the working directory