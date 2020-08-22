```py
# There may be some times where you need to split a string on a comma or colon.

# This will split the string on ":" and will grab the first element of the string array that was created.
df['Reason'] = df.title.apply(lambda x: x.split(':')[0])
df
```
