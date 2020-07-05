```py
import numpy as np
import pandas as pd

df = pd.DataFrame({'A': [1,2,6, 4],
                   'B': [4,np.nan,10,np.nan],
                   'C': [98, np.nan, np.nan, np.nan]})

print(df)
print('-----+++++-----')
# Drop rows containing nulls
print(df.dropna())
print('-----+++++-----')
# Drop cols containing nulls
print(df.dropna(1))

# Fill in 12 where col B has a null value
df['A'] = df['B'].fillna(12)

print(df)

# Fill in null b vals with the avg of B
df['B'] = df['B'].fillna(df['B'].mean())

print(df)

```
