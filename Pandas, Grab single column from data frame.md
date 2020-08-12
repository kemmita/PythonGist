```py
import numpy as np
import pandas as pd 

# Read CSV
df = pd.read_csv('sample_data/california_housing_test.csv')

# Convert col into a Pandas Series to work on a single col
longitude = df.longitude

longitude.where(lambda x : x > -114.67).dropna()
```
