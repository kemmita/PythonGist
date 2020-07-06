```py
import numpy as np
import pandas as pd 

df = pd.read_csv('Universities.csv')

# Specify the col name and then use the idxmax funciton
df['Completions'].idxmax()

# You can then grab the value using the index above
max_n = df['Completions'][df['Completions'].idxmax()]
```
