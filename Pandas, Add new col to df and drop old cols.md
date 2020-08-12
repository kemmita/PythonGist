```py
import numpy as np
import pandas as pd 

# Read CSV
df = pd.read_csv('sample_data/california_housing_test.csv')

# Add a col to the df
df['old_people'] = df.housing_median_age > 40

# Drop a col
df.drop('households', axis=1,inplace=True)
```
