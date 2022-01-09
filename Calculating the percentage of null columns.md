```py
def percent_null(df):
  percent_null = (100*(df.isnull().sum() / len(df)))
  return percent_null[percent_null > 0].sort_values()
  
percent_null(df)  
```
