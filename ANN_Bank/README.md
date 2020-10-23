# Predict customers who will exit the bank

## Description
  Our problem is to predict customers who will exit the bank, which is classification. 

## Data

This is the data of 5 rows.

|RowNumber|CustomerId|Surname|CreditScore|Geography|Gender|Age|Tenure|Balance|NumOfProducts|HasCrCard|IsActiveMember|EstimatedSalary|Exited|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|1|15634602|Hargrave|619|France|Female|42|2|0|1|1|1|101348.88|1|
|2|15647311|Hill|608|Spain|Female|41|1|83807.86|1|0|1|112542.58|0|
|3|15619304|Onio|502|France|Female|42|8|159660.8|3|1|0|113931.57|1|
|4|15701354|Boni|699|France|Female|39|1|0|2|0|0|93826.63|0|
|5|15737888|Mitchell|850|Spain|Female|43|2|125510.82|1|1|1|79084.1|0|

1. RowNumber: Index of customer
2. CustomerId: Number of custiners' identity
3. Surname: Name of customer
4. CreditScore: Credit Score 
5. Geography: Country
6. Gender: Gender
7. Age: Age
8. Tenure: Tenure
9. Balance: Balance
10. NumOfProducts: Number of Products
11. HasCrCard: Has the credict card 
12. IsActiveMember: The person is active
13. EstimatedSalary: Estimated Salary
14. Exited: Leave the bank

## Problem

There are some problems in the dataset. 
1. Time series: inser_date, start_date and end_date 
2. Categorical: origin, destination, train type, train_class and fare.
3. Missing data: price, train_class and fare. 
4. The dataset which is too big is 7644664 rows x 52 columns. 

||Columns type|Number of missing data|
|---|---|---|
|insert_date|datetime64[ns]|0|
|origin|object|0|
|destination|object|0|
|start_date|datetime64[ns]|0|
|end_date|datetime64[ns]|0|
|train_type|object|0|
|price|float64|573121|
|train_class|object|26690|
|fare|object|26690|

## Preprocessing
### Number of Data
  We use train_test_split from scikit- learn to decrease the sample because the dataset is too large, so we use 10% of dataset to be trained. Moreover, we split datasets again, which Training set is 90% of dataset and testing data is 10% of dataset.
### Time Series
  1. We divid the feature of insert_date to the features of month, day, hour, minute and second. We don’t need the feature of year because all features of year are the same.

|Insert_date minimum date time|Insert_date maximum date time|
|---|---|
|2019-04-11 21:49:46|2019-05-09 21:19:16|

|Insert_date|Insert_month|Insert_day|Insert_hour|Insert_min|Insert_sec|
|---|---|---|---|---|---|
|2019-04-11 21:49:46|04|11|21|49|46|

  2. The features of start_date and end_date are time series, so we change the datetime to hour, which we calculate between start_date and end_date to represent the features of start_date and end_date because all of people spent less than one day taking the train.

|start_date|end_date|start_end_hour|
|---|---|---|
|2019-04-18 05:50:00|2019-04-18 08:55:00|3.083333|
  
### Categorical
  1. RandomForest: Directly convert into code
  2. Linear regression: one hot encoding
### Missing data
  We drop the data which has empty value because there are at least 70000000x52 data in the dataset, which doesn’t affect the result a lot. Moreover, for the price part, we fill the mean of price.
### Feature selection
##### Ridge
![Ridge_coef](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)
##### Lasso
![Lasso_coef](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Lasso_coef.png)
##### Random Forest
![Random_coef](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/Random_coef.png)

## Result
1000 samples
### Linear Regression with Ridge
![Ridge_result](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_result.png)
![Ridge_curve](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_curve.png)
### Linear Regression with Lasso
![Lasso_result](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Lasso_result.png)
![Lasso_curve](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Lasso_curve.png)
### Random Forest Regression
![Random_result](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/Random_result.png)
![Random_curve](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/Random_curve.png)
### Comparation
||LR with Ridge|LR with Lasso|Random Forest|
| --- | --- | --- | --- |
|MSE|129.67215|129.68961|90.71796|
|R square|0.78991|0.78988|0.85302|
|Train score|0.78541|0.78540|0.97121|
|Test score|0.78991|0.78988|0.85302|

## Conclusions
1. The data doesn't complete yet, especially the linear regression because we can increase the degree to compute the best result. However, we need enough time and good computer to run the data.
2. Also for the Random Forest, we only try 10 and 100 trees. there are other parameter we can try.

