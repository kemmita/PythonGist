```py
import numpy as np
import pandas as pd 

df = pd.read_csv('african_econ_crises.csv')

# we want the first year Kenya had a systemic_crises, instead of using head(1) to get the top row, use iloc[0]
# you will then have the first row with the data we want, then simply append the col you want "['year']" at the end of the query
g = df[(df.country == 'Kenya') & (df.systemic_crisis == 1)].sort_values(by='year').iloc[0]['year']
```
