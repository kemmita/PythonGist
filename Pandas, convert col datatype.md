```py 
import pandas as pd

# Import CSV
df = pd.read_csv('911.csv')

# Convert entire col to a new datatype, in this case str to timestamp
df['timeStamp'] = pd.to_datetime(df.timeStamp)
```

Below we convert all float cols to in
```py
for i in df.columns:
  if df[i].dtype == np.float:
    df[i] = df[i].astype(int)
```
