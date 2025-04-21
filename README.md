# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn
## NAME: PAVITHRA S
## REG NO:212223220073
## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import Libraries and Load Dataset.
2.Preprocess the Data.
3.Split the Dataset.
4.Train the Decision Tree Classifier.
5.Make Predictions and Evaluate the Model
 

## Program:
```
import pandas as pd
data=pd.read_csv("Employee.csv")
data
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/d6ea7364-670f-4bec-a849-8d94a29bf4ab)

```
data["left"].value_counts()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/a7f877dd-240b-4acf-9cde-0dfaecce158c)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
```
```
data.head()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/a32597d8-d198-4719-8fed-c30ffad90e31)

```
data["salary"]=le.fit_transform(data["salary"])
data
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/cfe9fd00-9d1d-4d1b-8a3d-220860122117)
```
x=data[["satisfaction_level","last_evaluation","number_project","time_spend_company"]]
x.head()
```
![image](https://github.com/user-attachments/assets/57790e34-a248-4b71-988c-d5ad9e6533c6)
```
y=data["left"]
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
```
```
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
```
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:

![image](https://github.com/user-attachments/assets/b937d1c3-fd7f-44a6-8ea5-52d5fcc1657c)

## Output:

![image](https://github.com/user-attachments/assets/4e82445d-152a-47bf-b560-e5c46473c536)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
