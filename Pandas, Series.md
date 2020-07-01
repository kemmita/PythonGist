```py
import pandas as pd

# Series in Pandas allow us to work with vectors as we would in nump, but we can apply keys here
salesQ1 = pd.Series(data=[150, 333, 565, 399], index=['USA', 'Brazil', 'China', 'Korea'])
salesQ2 = pd.Series(data=[150, 333, 565, 399], index=['USA', 'Brazil', 'China', 'Russia'])

# We can access an elem within the series using either index name or index num
print(salesQ1['China'])
print(salesQ1[2])

# When performing operations on 2 series, if they do not share the same index name, the operation cannot be performed
print(salesQ1 + salesQ2)
```
