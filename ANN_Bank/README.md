# Predict customers who will leave the bank

## Description
  Our problem is to predict customers who will leave the bank, which is classification. 

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
8. Tenure: How long does person use this bank
9. Balance: Balance
10. NumOfProducts: Number of Products
11. HasCrCard: Has the credict card 
12. IsActiveMember: The person is active
13. EstimatedSalary: Estimated Salary
14. Exited: Leave the bank

## Problem

There are some problems in the dataset. 
Categorical: Surname, Geography, Gender


## Preprocessing

### Categorical
  1. RandomForest: Directly convert into code
  2. Linear regression: one hot encoding

## Result


## Conclusions
1. The data doesn't complete yet, especially the linear regression because we can increase the degree to compute the best result. However, we need enough time and good computer to run the data.
2. Also for the Random Forest, we only try 10 and 100 trees. there are other parameter we can try.

