```py
#!/home/bumluck/miniconda3/bin/python3

x = 10
a = 19
old_enough = False

if x > 7 and a > 17:
    print('and operator')


if x > 18 or a < 45:
    print('or operator')


if not old_enough:
    print('not operator')

# Use all for multiple and operators
if all([x > 8, x<98, a == 19]):
    print('all operator')

# Use any for multiple or operators
if any([x == 10, a > 877, x < 1]):
    print('any operator')


```
