```py
import numpy as np


# x = months in a year, independent var
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])

# y = sales in month, the data is in order, dependent var
y = np.array([25, 38, 29, 115, 82, 114, 120, 160, 153, 190, 239, 175])

# The regression formula 
# y = y, x= x, m = slope, b = y intercept
# yhat = mx + b


# n = the number of data points we have, which is 12. Reference"nsumxy" = n * sum(x*y)
# we first need to find the slope the formula for that is m = (nsumxy - sumxsumy) / (nsumx^2 - sumx^2)

def slope(x, y):
  n = len(x)
  sum_x = sum(x)
  sum_xsq = sum(np.square(x))
  sum_x_sq = sum(x)**2
  sum_y = sum(y)
  product_xy = sum(x * y)
  numerator = (n * product_xy) - (sum_x * sum_y)
  denominator = (n * sum_xsq) - (sum_x_sq)  
  return round(numerator / denominator, 4)


# Now we need to find the y intercept, formula b = sumy-msumx / n

def y_intercept(x, y):
  sum_y = sum(y)
  sum_x = sum(x)
  n = len(x)
  m = slope(x, y)
  return round(((sum_y - (m * sum_x)) / n), 1)

def kemmit_regression(m,x,b):
  return ((m * x) + b) 
  
#  The root mean square error will tell us about how much our dots will deviate from the applied regression line, the smaller the better.

actual = y
predicted = kemmit_regression(slope(x, y), x, y_intercept(x, y)) 

rmse = np.round(np.sqrt(sum((actual - predicted)**2) / (len(x) - 1)), 1)

print(rmse)  
```

