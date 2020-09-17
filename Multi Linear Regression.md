```py
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats
from IPython.display import Math,display 

# STEP 1 Multiple Linear Regression, first step is to determin if our dependent variable has a significant corelation with the independent variables using correlation coeficient formula if it does not it will be removed

# House Prices
y = np.array([300000.00,400000.00,900000.00,1000000.00,250000.00])

# Number of Rooms
x1 = np.array([4,5,8,8,4])

# Ears Old 
x2 = np.array([10,10,6,3,20])


# Correlation Coeficient
display(Math(' r = \\frac{\sum_{i-1}^n(x_{i} - \overline{x})(y_{i} - \overline{y})}{\\sqrt{\sum_{i-1}^n(x_{i} - \overline{x})^2 \sum_{i-1}^n(y_{i} - \overline{y})^2 }} '))
display(Math('\\textrm{}'))
cf1 = np.corrcoef(np.vstack((y,x1)))
cf2 = np.corrcoef(np.vstack((y,x2)))


# STEP 2 determine if we have any multicolinearity between our independent variables, if we do, we will want to remove one. We will use the correlation coeficient to determine this.
cf3 = np.corrcoef(np.vstack((x1,x2)))

# STEP 3 find the b1 and b2 "our coeficients"
#  Multi Lin Regression formula 
display(Math(' y = b_{0} + b_{1}x_{1} + b_{2}x_{2} '))
display(Math('\\textrm{}'))
# Formula for b1 and b2
display(Math('b1 = \\frac{(\sum x_{2^2})(\sum x_{1}y) - (\sum x_{1}x_{2})(\sum x_{2}y)}{(\sum x_{1^2})(\sum x_{2^2}) - (\sum x_{1}x_{2})^2} '))
display(Math('\\textrm{}'))
display(Math('b2 = \\frac{(\sum x_{1^2})(\sum x_{2}y) - (\sum x_{1}x_{2})(\sum x_{1}y)}{(\sum x_{1^2})(\sum x_{2^2}) - (\sum x_{1}x_{2})^2} '))
display(Math('\\textrm{}'))

# The b1 and b2 formulas have (\sum x_{2^2}) and (\sum x_{1^2}) we can not read this to be true, there is a formula used to get these two place holder above
display(Math('\sum x_{1^2} = \sum x_{1^2} - \\frac{(\sum x_{1})^2}{N} '))
display(Math('\\textrm{}'))
display(Math('\sum x_{2^2} = \sum x_{2^2} - \\frac{(\sum x_{2})^2}{N} '))
display(Math('\\textrm{}'))
sum_x1_sq = (sum(x1**2)) - ((sum(x1)**2) / len(x1))
sum_x2_sq = (sum(x2**2)) - ((sum(x2)**2) / len(x2))

# The b1 and b2 formulas have \sum x_{i}y we can not read this to be true there is a formula we must use to get this value
display(Math('\sum x_{1}y = \sum x_{1}y - \\frac{(\sum x_{1})(\sum y)}{N} '))
display(Math('\\textrm{}'))
display(Math('\sum x_{2}y = \sum x_{2}y - \\frac{(\sum x_{2})(\sum y)}{N} '))
display(Math('\\textrm{}'))
sum_x1_y = (sum(x1*y)) - ((sum(x1) * sum(y)) / len(x1))
sum_x2_y = (sum(x2*y)) - ((sum(x2) * sum(y)) / len(x2))

# The b1 and b2 formulas have \sum x_{1}x_{2} we can not read this to be true there is a formula we must use to get this value
display(Math('\sum x_{1}x_{2} = \sum x_{1}x_{2} - \\frac{(\sum x_{1})(\sum x_{2})}{N} '))
display(Math('\\textrm{}'))
sum_x1_x2 = (sum(x1*x2)) - ((sum(x1) * sum(x2)) / len(x1))

# Calculate b1 and b2
b1 = np.round(((sum_x2_sq * sum_x1_y) - (sum_x1_x2 * sum_x2_y)) / ((sum_x1_sq * sum_x2_sq) - sum_x1_x2**2),4)
b2 = np.round(((sum_x1_sq * sum_x2_y) - (sum_x1_x2 * sum_x1_y)) / ((sum_x1_sq * sum_x2_sq) - sum_x1_x2**2),4)

# Calculate b0
display(Math('b_{0} = \overline y - b_{1} \overline x1 - b_{2} \overline x2 '))
display(Math('\\textrm{}'))

b0 = np.round(np.mean(y) - (b1 * np.mean(x1)) - (b2 * np.mean(x2)),4)

# The below example shows a home with 4 bedrooms and 10 years of age, run the regression to view the expected price.
def multi_linear_regression():
  return b0 + b1*4 + b2*10

multi_linear_regression()
```
