```py
import numpy as np
from IPython.display import Math,display 
import matplotlib.pyplot as plt

arr = np.array([12,454,23,98,45,66,90])

def min_max_transformation(x):
  return (x - np.min(arr)) / (np.max(arr) - np.min(arr))

scaled = np.vectorize(myfunc)(arr)
plt.title(display(Math(' x_{scaled} = \\frac{x_{i} - x_{min}}{x_{max} - x_{min}}')))
plt.plot(scaled)
```
