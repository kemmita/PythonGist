```py
import numpy as np
import pandas as pd

index = ['A', 'B', 'C', 'D', 'E']
columns = ['W', 'X', 'Y', 'Z']

np.random.seed(42)
data = np.random.randint(-100, 100, (5, 4))

#  Create a Data Frame
df = pd.DataFrame(data, index, columns)

# Access an entire column, you can then perform mean and other ops on it.
df['W']
# Access an entire row
a = df.loc['A']

# Access multiple columns.
df[['W', 'Z']]
# Access multiple rows.
df.loc[['A', 'B']]


# Create a new column
df['new'] = df['W'] + df['Y']
# Create a new row
df.loc['NEW'] = df.loc['D'] + df.loc['E']

# Remove a column, if we did not specify one, pd would try to remove a row and not a col
df2 = df.drop('new', 1)
# Remove a row
df3 = df.drop('C')

# Select a value at a specific row and column
df4 = df.loc['A', 'W']

# Select multiple rows for multiple columns
df5 = df.loc[['A', 'B'], ['W', 'Z']]
```
