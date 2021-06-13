```py
#!/home/fatguyrus/miniconda3/bin/python3
import sys

# We skip the first  arg as that will be the name of the file.
for i in sys.argv[1:]:
    if not any([i.isdigit(), i.isdecimal()]):
        print(i.upper())   
```
