```py
#!/home/fatboyruss/miniconda3/bin/python3
import sys

# Generic exception when you do not know the type of the error
try:
    print('7' + 5)
except Exception as e:
    print(e)

# Specific error when you know the type of the error
try:
    print(2 / 0)
except ZeroDivisionError:
    print("Division with 0 is not possible")

# You can combine as many exception types as needed
try:
    print('9' + 8)
except TypeError as e:
    print(f'adding {type("9")} with type {type(8)} is not permitted')
except Exception as e:
    print(e)

if int(sys.argv[1]) > 18:
    raise ValueError('Too old to attend this grade.')
else:
    print('Welcome to your senior year at school')
```
