# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load Data – Import the dataset containing employee details and their salaries.

2. Preprocess Data – Handle missing values, encode categorical variables, and split into training and test sets.

3. Initialize Model – Create a DecisionTreeRegressor with suitable parameters (e.g., max_depth=5).

4. Train Model – Fit the regressor using training data (model.fit(X_train, y_train)).

5. Predict & Evaluate – Predict salaries on test data and evaluate using metrics like MAE, MSE, and R² score.

6. Visualize & Interpret – Plot the tree and analyze feature importance for salary prediction.
 

## Program and output:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Dhanusya K
RegisterNumber:  212223230043
*/
```
~~~
import pandas as pd
data=pd.read_csv("C:\\Users\\admin\\OneDrive\\Desktop\\Folders\\ML\\DATASET-20250226\\Salary.csv")
data.head()
~~~
![436601688-fb7e5837-fa27-4dd2-9fc8-87b5072ac334](https://github.com/user-attachments/assets/47030562-a00f-42db-a9eb-4e2e1c8ca875)
~~~
data.info()
data.isnull().sum()
~~~
![436602010-e898c62f-8a56-4b06-9149-7b960db1ea02](https://github.com/user-attachments/assets/b225ef78-2f29-4105-9d8c-89f3c617d8e7)
~~~
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
~~~
![436602261-b7b88868-579e-498d-9114-e41159ff1733](https://github.com/user-attachments/assets/f7512148-9909-42c3-8fa5-f689d5d0488a)
~~~
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()
~~~
![436602652-af7af4d2-82a1-4f1f-88e7-6f2347954aeb](https://github.com/user-attachments/assets/a816e9d3-fc52-44a8-b08f-2918c93ebe7f)
~~~
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
~~~
![436602983-06fd2d05-c429-4c48-83e1-6038dbe82145](https://github.com/user-attachments/assets/fe9f5e81-9cd4-460e-b71d-6b7fbd81969b)
~~~
from sklearn import metrics
from sklearn.metrics import r2_score
r2 = r2_score(y_test, y_pred)
r2
~~~
![436603318-3f40d399-0f10-4ab7-8117-86ab06f5c8b1](https://github.com/user-attachments/assets/6b2a0737-f2f4-4503-9bf7-12461a9e7645)
~~~
dt.predict([[5,6]])
~~~
![436603624-5bddfaf6-ef95-4654-8526-11fea921f807](https://github.com/user-attachments/assets/36c42091-39aa-42d5-b14b-8a45ce757e43)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
