```py
import numpy as np
import pandas as pd 

# Read CSV
df = pd.read_csv('sample_data/california_housing_test.csv')

df.longitude[0] = np.nan

# Drop any row containing a null value
df.dropna()

# Any col val of null in col longitude will now have the value of the mean of the entire longitude series
df['longitude'] = df['longitude'].fillna(df.longitude.mean())
```
