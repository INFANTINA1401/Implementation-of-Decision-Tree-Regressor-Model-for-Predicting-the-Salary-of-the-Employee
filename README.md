# EX:9 Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2. Calculate the null values present in the dataset and apply label encoder.
3. Determine test and training data set and apply decison tree regression in dataset.
4. Calculate Mean square error,data prediction and r2.

## Program:

Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
# Developed by: INFANTINA MARIA L 
# RegisterNumber: 212223100013

```
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
```
![image](https://github.com/user-attachments/assets/44224a2c-9588-46f9-b528-832d572de482)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![image](https://github.com/user-attachments/assets/9edede77-5ba8-43cb-922e-79b4112d9af8)
```
x=data[["Position","Level"]]
y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
```
![image](https://github.com/user-attachments/assets/2988cf9f-9792-4c8f-9681-11e198b4a6ba)
```
r2=metrics.r2_score(y_test,y_pred)
r2
```
![image](https://github.com/user-attachments/assets/4f454edc-ef6f-499c-b441-9c6a10fe1f4d)
```
dt.predict([[5,6]])
```
![image](https://github.com/user-attachments/assets/ec3db4a9-837a-4692-bcea-788278c1f5ba)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
