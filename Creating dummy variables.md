```py
my_object_columns = df.select_dtypes(include='object')
my_numeric_columns = df.select_dtypes(exclude='object')
df_object_dummies = pd.get_dummies(my_object_columns,drop_first=True)
df_object_dummies

final_df = pd.concat([my_numeric_columns,df_object_dummies],axis=1)
final_df
```
