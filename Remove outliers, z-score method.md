```py
import numpy as np
from IPython.display import Math,display 
import matplotlib.pyplot as plt
from scipy import stats

arra = np.array([12,454,23,98,45,66,90,77,15,93,1000,41,150])
z_scored = stats.zscore(arra)

display(Math('\huge z_{i} = \\frac{x_{i} - \overline{x} }{\\sigma_{x}}'))

def remove_outliers(z, ar):
  indexes_to_remove = np.where((z > 3) | (z < -3))
  for i in indexes_to_remove:
    z = np.delete(z, i)
    ar = np.delete(ar, i)
  return (z, ar)

out_removed = remove_outliers(z_scored, arra)

z_scored = out_removed[0]
arra = out_removed[1]
```
