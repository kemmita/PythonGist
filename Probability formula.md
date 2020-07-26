```py
import numpy as np
from IPython.display import Math,display 
import matplotlib.pyplot as plt
from scipy import stats

# Probability formula. The chance / all chances. Multiply by 100 to convert decimal to percentage
display(Math('\huge p_{i} = \\frac{100 c_{i}}{\\sum c}'))

def probability(x,y):
  return np.round((x*100)/y, 1)

probability(20,90)
```
