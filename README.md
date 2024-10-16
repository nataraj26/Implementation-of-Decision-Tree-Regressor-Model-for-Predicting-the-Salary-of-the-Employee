# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset.
5. Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by:    NATARAJ KUMARAN S
RegisterNumber:  212223230137
*/
```

```
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
```
<img width="450" alt="image" src="https://github.com/user-attachments/assets/c98b586a-147f-46a3-bc2c-d38502ec476e">


```
data.info()
data.isnull().sum()
```
<img width="650" alt="image" src="https://github.com/user-attachments/assets/7cacd016-60ea-4241-926f-e1aa248416cd">

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
<img width="450" alt="image" src="https://github.com/user-attachments/assets/6911895c-1cea-447f-add8-ed1847afa2cc">

```
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
xtrain,xtest,ytrain,ytest=train_test_split(x,y,test_size=0.2,random_state=1)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(xtrain,ytrain)
y_pred=dt.predict(xtest)
print(y_pred)
```
<img width="450" alt="image" src="https://github.com/user-attachments/assets/570160df-d41b-453f-af28-6c59c2ff25be">

```
from sklearn.metrics import mean_squared_error
mse=mean_squared_error(ytest,y_pred)
print(mse)
```
<img width="650" alt="image" src="https://github.com/user-attachments/assets/f2a883a4-6f6c-42e8-bc99-e5b432efb63f">

```
r2=metrics.r2_score(ytest,y_pred)
print(r2)
```
<img width="650" alt="image" src="https://github.com/user-attachments/assets/5049d3ed-cc16-4b20-9ce4-5690e50ab9bb">

```
dt.predict([[5,6]])
```
<img width="1350" alt="image" src="https://github.com/user-attachments/assets/7bf9ea1f-411b-403c-bdf2-ce990a3cfbb4">


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
