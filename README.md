# BLENDED_LEARNING
# Implementation-of-Linear-Regression-for-Predicting-Car-Prices
## AIM:
To write a program to predict car prices using a linear regression model and test the assumptions for linear regression.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import required libraries and load the car price dataset.
2.Select features and split the data into training and testing sets.
3.Train the Linear Regression model using the training data.
4.Predict prices and evaluate the model using performance metrics. 


## Program:
```
/*
 Program to implement linear regression model for predicting car prices and test assumptions.
Developed by: P.PRIYADHARSHINI
RegisterNumber:  212225220076

import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error,r2_score,mean_absolute_error
from sklearn.preprocessing import StandardScaler
import matplotlib.pyplot as plt
import seaborn as sns
import statsmodels.api as sm
df=pd.read_csv('CarPrice_Assignment.csv')
df.head()
X= df[['enginesize', 'horsepower', 'citympg', 'highwaympg']]
y= df['price']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2,random
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
model = LinearRegression()
model.fit(X_train_scaled, y_train)
y_pred = model.predict(X_test_scaled)
print('P.PRIYADHARSHINI')
print('25012009')
print("MODEL COEFFICIENTS:")
for feature,coef in zip(X.columns,model.coef_):
print(f"{feature:>12}: {coef:>10.2f}")
print(f"{'Intercept':>12}: {model.intercept_:>10.2f}")
print("\nMODEL PERFORMANCE:")
print(f"{'MSE :>12'}: {mean_squared_error(y_test,y_pred):>10.2f}")
print(f"{'RMSE':>12}: {np.sqrt(mean_squared_error(y_test,y_pred)):>10.2f}")
print(f"{'R-squared':>12}:{r2_score(y_test,y_pred):>10.2f}")
P.PRIYADHARSHINI
25012009
MODEL COEFFICIENTS:
enginesize:    4523.40
horsepower:    1694.22
citympg:    -392.57
highwaympg:    -816.36
Intercept:   13223.41
MODEL PERFORMANCE:
MSE :>12: 16471505.90
RMSE:    4058.51
R-squared:      0.79
print(f"{'MAE :>12'}: {mean_absolute_error(y_test,y_pred):>10.2f}")
MAE :>12:    2892.63
plt.figure(figsize=(10, 5))
plt.scatter(y_test, y_pred, alpha=0.6)
plt.plot([y.min(), y.max()], [y.min(), y.max()], 'r--')
plt.title("Linearity Check: Actual vs Predicted Prices")
plt.xlabel("Actual Price ($)")
plt.ylabel("Predicted Price ($)")
plt.grid(True)
plt.show()
residuals = y_test - y_pred
dw_test = sm.stats.durbin_watson(residuals)
print(f"\nDurbin-Watson Statistics: {dw_test:.2f}",
"\n(Values close to 2 indicate no autocorrelation)")
Durbin-Watson Statistics: 2.28 
(Values close to 2 indicate no autocorrelation)

plt.figure(figsize=(10, 5))
sns.residplot(x=y_pred, y=residuals, lowess=True, line_kws={'color': 'red'})
plt.title("Homoscedasticity Check: Residuals vs Predicted")
plt.xlabel("Predicted Price ($)")
plt.ylabel("Residuals ($)")
plt.grid(True)
plt.show()
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))
sns.histplot(residuals, kde=True, ax=ax1)
ax1.set_title("Residuals Distribution")
sm.qqplot(residuals, line='45', fit=True, ax=ax2)
ax2.set_title("Q-Q Plot")
plt.tight_layout()
plt.show()
*/
```

## Output:
![WhatsApp Image 2026-03-28 at 4 18 32 PM](https://github.com/user-attachments/assets/fbe6c3d3-2a53-406f-907c-dd4a36bb16f7)




![WhatsApp Image 2026-03-28 at 4 18 56 PM](https://github.com/user-attachments/assets/2200b9c0-6a1c-489b-b05f-8b9951ff850e)



![WhatsApp Image 2026-03-28 at 4 19 42 PM](https://github.com/user-attachments/assets/86cbe53b-70be-4980-88d6-65eb6604087c)



![WhatsApp Image 2026-03-28 at 4 20 32 PM](https://github.com/user-attachments/assets/2bfc530d-19b9-492e-895e-cf560ba20e4e)



![WhatsApp Image 2026-03-28 at 4 20 53 PM](https://github.com/user-attachments/assets/9e4fbc24-0b59-486d-a94c-3a788b7f072b)

## Result:
Thus, the program to implement a linear regression model for predicting car prices is written and verified using Python programming, along with the testing of key assumptions for linear regression.
