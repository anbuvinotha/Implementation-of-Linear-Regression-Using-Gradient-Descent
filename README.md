# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the dataset from '50_Startups.csv'.
2. Extract features 'x' and target 'y'.
3. Convert 'x' to float type and standardize using StandardScaler.
4. Standardize the target 'y' using StandardScaler.
5. Add a bias term (column of ones) to the feature matrix 'x1'.
6. Initialize the parameter vector 'theta' to zeros.
7. For each iteration in the specified range (num_iters): a. Compute predictions: y_hat = x.dot(theta). b. Compute the error: error = y_hat - y. c. Update theta using the gradient descent formula: theta = theta - (learning_rate / m) * x.T.dot(error).
8. Scale new input data using the fitted scaler.
9. Add bias term (1) to the scaled new data.
10. Compute the predicted value using the new scaled data and theta: prediction = np.dot(new_data, theta).
11. Inverse scale the prediction to get the final output.
12. Print the predicted value. .

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: ANBU VINOTHA S
RegisterNumber:  212223230015

import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(x1,y,learning_rate=0.01,num_iters=1000):
    x=np.c_[np.ones(len(x1)),x1]
    theta=np.zeros(x.shape[1]).reshape(-1,1)
    for _ in range (num_iters):
        predictions=(x).dot(theta).reshape(-1,1)
        errors=(predictions - y).reshape(-1,1)
        theta-= learning_rate*(1/len(x1))*x.T.dot(errors)
    return theta
data = pd.read_csv('50_Startups.csv',header=None)
print(data.head())
x=(data.iloc[1:, :-2].values)
print(x)
x1=x.astype(float)
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
print(y) x1_scaled=scaler.fit_transform(x1)
y1_scaled=scaler.fit_transform(y)
print(x1_scaled)
print(y1_scaled)
theta=linear_regression(x1_scaled,y1_scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_scaled = scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(f"Predicted value: {pre}")


*/
```

## Output 1:
![image](https://github.com/user-attachments/assets/db5a9c7a-708f-47dd-a462-eee3cc737bf6)

## Output 2:
![image](https://github.com/user-attachments/assets/674b560e-ace1-4c60-b409-5ab84ec62768)




## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
