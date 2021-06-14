```py
#!/home/fatboyrus/miniconda3/bin/python3

# This function can take n arguments
def display(*arg):
    for i in arg:
        print(i)


display(1, 2, 4, 'eddede')
display(1, 2, 'eddede', 2, 3, 5)


# This function can take a dict with n keys
def display_two(**kwargs):
    for i in kwargs.values():
        print(i)


display_two(a=19, b='s')
display_two(a=19, b='s', c=14)

```
