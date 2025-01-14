# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
### Step1
Import the standard Libraries. 

### Step2
Set variables for assigning dataset values.

### Step3 
Import linear regression from sklearn.

### Step4
Assign the points for representing in the graph.

### Step5
Predict the regression for marks by using the representation of the graph.

### Step6
Compare the graphs and hence we obtained the linear regression for the given datas.




## Program:

Program to implement the simple linear regression model for predicting the marks scored.
## Developed by: Gumma Dileep Kumar
## RegisterNumber: 212222240032
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
df.head()
df.tail()
x = df.iloc[:,:-1].values
x
y = df.iloc[:,1].values
y
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
y_pred
y_test
#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='purple')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
#Graph plot for test data
plt.scatter(x_test,y_test,color='red')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)
``` 



## Output:

### df.head()
![model](ML_ex-2.1.png)

### df.tail()
![model](ML_exp-2.2.png)

### Array of value X
![model](ML_exp-2.3.png)

### Array of value Y
![model](ML_exp-2.4.png)

### Values of Y prediction
![model](ML_exp-2.5.png)

### Array values of Y test
![model](ML_exp-2.6.png)

### Training Set Graph & Test Set Graph
![model](ML_exp-2.7.png)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
