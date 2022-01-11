```py
# imports
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split, cross_val_score, GridSearchCV
from sklearn.linear_model import LinearRegression, Ridge, RidgeCV, Lasso, LassoCV, ElasticNet
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score, mean_absolute_percentage_error, SCORERS
from sklearn.preprocessing import PolynomialFeatures, StandardScaler

# read in data
df = pd.read_csv('AMES_Final_DF.csv')
df

# Train test split
X = df.drop('SalePrice', axis=1)
y = df['SalePrice']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.1, random_state=101)

# scale features
scaler = StandardScaler()
scaler.fit(X_train)
scaled_X_train = scaler.transform(X_train)
scaled_X_test = scaler.transform(X_test)

# create elastic net model
base_elastic_model = ElasticNet(max_iters=1000000)

# Use grid search to locate best hyper params for elastic net
param_grid = {'alpha':[0.1,1,5,10,100], 'l1_ratio':[.1,.7,.99,1]}
grid_model = GridSearchCV(estimator=base_elastic_model,param_grid=param_grid,scoring='neg_mean_squared_error',cv=5,verbose=1)

# train elastic net
grid_model.fit(scaled_X_train, y_train)

# view best hyper params
grid_model.best_params_

# get predictions and and guage model performance
y_pred = grid_model.predict(scaled_X_test)
mean_squared_error(y_test, y_pred)
```
