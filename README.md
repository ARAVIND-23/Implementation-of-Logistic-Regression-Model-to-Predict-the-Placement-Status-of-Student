# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required packages and print the present data.
2.Print the placement data and salary data.
3.Find the null and duplicate values.
4.Using logistic regression find the predicted values of accuracy , confusion matrices.
5.Display the results.
## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: ARAVIND G
RegisterNumber:  212223240011
*/
```
```
import pandas as pd

import numpy as np

from sklearn.model_selection import train_test_split

from sklearn.linear_model import LogisticRegression

df = pd.read_csv('Placement_Data_Full_Class (1).csv')

df.info()

df.drop('sl_no',axis=1,inplace=True)

df1 = ['gender','ssc_b','hsc_b','hsc_s','degree_t','workex','specialisation','status']

for col in df1:

df[f'{col}_c'] = df[col].astype('category').cat.codes
df.drop(columns=df1,inplace=True)

x = df.iloc[:,:-2].values

x.shape

y= df.iloc[:, -1].values

y

x.shape

y.shape

x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.3,random_state=1)

x_test.shape

x_train.shape

model = LogisticRegression()

model.fit(x_train,y_train)

y_pred = model.predict(x_test)

a = accuracy_score(y_test,y_pred)

print(a)
```

## Output:
![Screenshot 2024-11-11 230054](https://github.com/user-attachments/assets/93dcd94e-903c-4bcd-89bf-2c209219b0b6)

ACCURACY SCORE

![Screenshot 2024-11-11 230153](https://github.com/user-attachments/assets/92d460d5-286b-469b-be9a-dbada6012c02)


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
