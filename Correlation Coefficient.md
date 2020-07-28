```py
import numpy as np
from IPython.display import Math,display 
import matplotlib.pyplot as plt
from scipy import stats

# Covariance
display(Math('\huge c = \\frac{1}{n - 1} \sum_{i-1}^n(x_{i} - \overline{x})(y_{i} - \overline{y})'))
N = 66
height = np.random.randn(N)
weight = height + np.random.randn(N)
covariance = np.cov(np.vstack((height, weight)))


# Correlation Coeficient
display(Math('\huge r = \\frac{\sum_{i-1}^n(x_{i} - \overline{x})(y_{i} - \overline{y})}{\\sqrt{\sum_{i-1}^n(x_{i} - \overline{x})^2 \sum_{i-1}^n(y_{i} - \overline{y})^2 }} '))
cf = np.corrcoef(np.vstack((height,weight)))

plt.plot(height, weight,'kp',markerfacecolor='w',markersize=12)
plt.xlabel('Height')
plt.ylabel('Weight')
plt.show()

# Print the correlation coeficient
cf[1][0] * 100
```
