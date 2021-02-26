```py
rows_to_remove = []
for idx, val in enumerate(df['model']):
  if val.isdigit():
    print(val)
    rows_to_remove.append(idx)
```
