```py
import pandas as pd

# Get top 5 zip codes for 911 calls
df = pd.read_csv('911.csv')
df['zip'].value_counts().head(5)
```
