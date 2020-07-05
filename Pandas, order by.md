```py
import numpy as np
import pandas as pd 

df = pd.read_csv('Universities.csv')

df.groupby('University')['Completions'].sum().sort_values(ascending=False).head(20)
```
