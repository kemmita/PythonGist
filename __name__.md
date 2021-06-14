1. When another script imports an exisitng script you created it will execute the entire file if you do not inlucde __name__ in the file you created to be called.
```py
#!/home/a656375/miniconda3/bin/python3

def calling():
    print('calling')


if __name__ == "__main__":
    print('db helper file')
```
2. Now the file below that calls the file above will not execute the file and its contents until it is called.
```py
import exp

exp.calling()
```
