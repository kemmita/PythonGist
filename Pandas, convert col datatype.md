```py 
import pandas as pd

# Import CSV
df = pd.read_csv('911.csv')

# Convert entire col to a new datatype, in this case str to timestamp
df['timeStamp'] = pd.to_datetime(df.timeStamp)
```
