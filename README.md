# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee
## NAME: VMYTHILI
## REG NO: 212223040123

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the dataset Salary.csv using pandas and view the first few rows.

2.Check dataset information and identify any missing values.

3.Encode the categorical column "Position" into numerical values using LabelEncoder.

4.Define feature variables x as "Position" and "Level", and target variable y as "Salary".

5.Split the dataset into training and testing sets using an 80-20 split.

6.Create a DecisionTreeRegressor model instance.

7.Train the model using the training data.

8.Predict the salary values using the test data.

9.Evaluate the model using Mean Squared Error (MSE) and R² Score.

10.Use the trained model to predict salary for a new input [5, 6].

## Program:

/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: V MYTHILI
RegisterNumber:  212223040123
*/

```
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
```

```
data.isnull().sum()
```
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```

```
x=data[["Position","Level"]]
x.head()
```

```

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

```
r2=metrics.r2_score(y_test,y_pred)
r2
```

```
dt.predict([[5,6]])
```
## Output:


![image](https://github.com/user-attachments/assets/62d95776-8b83-4a31-9679-73dd352cb538)


![image](https://github.com/user-attachments/assets/fb87bb70-51c4-41ae-9b1a-9d115cbf1a93)


![image](https://github.com/user-attachments/assets/4ea52ac7-b5bc-4cc5-8613-179bd55876de)


![image](https://github.com/user-attachments/assets/065f7284-8cb6-4aa2-96fe-0810b00cb241)


![image](https://github.com/user-attachments/assets/8ce98f39-69a5-46f4-9cf5-88eda6ddf0e8)


![image](https://github.com/user-attachments/assets/20a60d73-7ae6-425b-a2f6-b364e2ee1a5a)


![image](https://github.com/user-attachments/assets/3eb5a3bf-1cd1-4734-bd27-653a2a22c49c)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
