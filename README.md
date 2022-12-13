# Support-Vector-Classifier-Strategy
In this notebook, we will learn to create a Support Vector Classifier (SVC) algorithm on NASDAQ Composite (^IXIC).

# 1. Import the libraries 
First, we will import the necessary libraries.

# 2. Read NASDAQ Data
The OHLC data for the index is stored in the Nasdaq.csv file. To read a CSV file, we can use read_csv method of pandas.

# 3. Define the explanatory variables
Explanatory or independent variables are used to predict the value. The X is a dataset that holds the features that SVC algorithm will use as independent variables for prediction. The X consists of variables such as Open - Close and High - Low. These can be understood as indicators based on which the algorithm will predict tomorrow's trend. The choice of using Open - Close and High - Lowas features is arbitrary.

# 4. Define the target variable 
Target variable is the outcome which the machine learning model will predict based on the explanatory variables. y is a target dataset storing the correct trading signal which the machine learning algorithm will try to predict. If tomorrow's price is greater than today's price then we will buy the NASDAQ Composite index, else we will have no position in the NASDAQ Composite index. We will store 1 for a buy signal and 0 for a no position in y.

# 5. Split the data into train and test
We will split data into training and test datasets. This is done so that we can fit the model on the training data and test the performance on the test data.
1. First, 80% of data is used for training and remaining data for testing.
2. X_train and y_train are train datasets.
3. X_test and y_test are test datasets.

# 6. Support Vector Classifier (SVC)
We will use SVC() function from sklearn.svm.SVC library to create our classifier model using fit() method on the training dataset.
We will use the predict method on the cls variable to predict the signals. We will pass X_test as the parameter to the predict method.

# 7. Classifier accuracy 
We will compute the accuracy of the algorithm on the train and test data set by comparing the actual values of signal with the predicted values of signal. The function accuracy_score() will be used to calculate the accuracy.

An accuracy of 57.76 % in test data suggests that the classifier model is effective.

# 8. Stratgey implementation 
We will predict the signal (buy or sell) using the cls.predict() function.
We will predict the signals on the entire dataset X. And then we will compute strategy returns based on the predicted signal, and then save it in the column cumulative_returns and plot the cumulative returns.
