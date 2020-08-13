```py
import numpy as np
import pandas as pd 

# Read CSV
df = pd.read_csv('sample_data/Salaries.csv')

# The select goes at the end "JobTitle" and the where goes first "df['EmployeeName'] == 'JOSEPH DRISCOLL'"
df[df['EmployeeName'] == 'JOSEPH DRISCOLL']['JobTitle']
```
