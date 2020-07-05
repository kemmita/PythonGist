```py
import numpy as np
import pandas as pd 

df = pd.read_csv('Universities.csv')

# group by uni and get the avg completions, return the top 20 rows.
df.groupby('University')['Completions'].mean().head(20)
```
