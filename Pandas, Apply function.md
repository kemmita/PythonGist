```py
import numpy as np
import pandas as pd 

# Read CSV
df = pd.read_csv('sample_data/Salaries.csv')

# Apply a function to each value in a col
df.TotalPay.apply(lambda x: np.sqrt(x))

def minus_sick_pay(x):
  return x - 900

df.TotalPay.apply(minus_sick_pay)  
```
