1. The current index is a,b,c,d,... we want to change it to 0, 1,....
```py
df = df.reset_index()
print(df.loc[0])
```
