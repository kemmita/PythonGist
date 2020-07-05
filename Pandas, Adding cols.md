1. Basic col creation
```py
import numpy as np
import pandas as pd 

df = pd.read_csv('Universities.csv')

# now each row will have a new col with a val of 10
df['new_cpol'] = 10
```

2. Applying functions to create a new col
```py
# return the first and last letter of the string
def grab_first_last(str):
    return str[0] + str[-1]

# new col will be titled First_Last and will contain the first and last letter for each University string found in the row 
df['First_Last'] = df['University'].apply(grab_first_last) 
```


