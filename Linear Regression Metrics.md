```py
display(Math('MAE = \\frac{1}{N} \\sum\limits_{i=1}^{N}|y_{i} - \hat y|'))

def mae(actual, prediction):
  return np.absolute(np.sum(actual-prediction)/len(actual))

print(mae(y_test, y_predict))

display(Math('MSE = \\frac{1}{N} \\sum\limits_{i=1}^{N}(y_{i} - \hat y)^2'))

def mse(actual, prediction):
  return np.square((np.sum(actual-prediction)/len(actual)))

print(mse(y_test, y_predict))

display(Math('RMSE = \\sqrt{\\frac{1}{N} \\sum\limits_{i=1}^{N}(y_{i} - \hat y)^2}'))

def rmse(actual, prediction):
  return np.sqrt(np.square((np.sum(actual-prediction)/len(actual))))

print(rmse(y_test, y_predict))

display(Math('R^2 = 1 -\\frac{\\sum\limits_{i=1}^{N}(y_{i} - \hat y_{i})^2}{\\sum\limits_{i=1}^{N}(y_{i} - \overline y)^2}'))

def r_sqaure(actual, predict):
  return np.round(1 - (np.sum(np.square(actual - predict)) / np.sum(np.square(actual - np.mean(actual)))),2)

  
r_sqaure(y_test, y_predict)
```
