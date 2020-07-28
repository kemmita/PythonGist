```py
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats
from IPython.display import Math,display 
# x = total bill
x = np.array([34.00,108.00, 64.00, 88.00, 99.00, 51.00])

# y = tip
y = np.array([5.00,17.00,11.00,8.00,14.00,5.00])

# y = y, x= x, m = slope, b = y intercept
display(Math('\huge \hat y = mx+b'))

# Code the formula above^^
def easy_regression(m,x,b):
  return np.round(((m*x) + b),2)

# Call the linregress function from Scipy with our two vecotrs defined above on line 7 and 10
regress = stats.linregress(x, y)

# call the function we created and pass the slope and intercept props returned from the scipy function
easy_regression(regress.slope, 87, regress.intercept)
```
