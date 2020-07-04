```py
import numpy as np
import pandas as pd

index = ['A', 'B', 'C', 'D', 'E']
columns = ['W', 'X', 'Y', 'Z']

np.random.seed(42)
data = np.random.randint(-100, 100, (5, 4))

#  Create a Data Frame
df = pd.DataFrame(data, index, columns)
print(df)
print('-----+++++-----')

# Filter a data frame
print(df[df > 34])
print('-----+++++-----')

#  Filter on column x greater than 10
print(df[df['X'] > 0])
print('-----+++++-----')

# Filter on multiple conditions, wrap each condition on with parens
print(df[(df['W'] > 0) & (df['Y'] > 10)])

```
