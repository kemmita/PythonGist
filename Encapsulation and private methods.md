```py
#!/home/fatboyrus/miniconda3/bin/python3

class Animal(object):
    def __init__(self, name, species):
        # Below is how you create private properties
        self.__name = name
        self.__species = species

    def display(self):
        self.__correct_name()
        print(self.__name)
        print(self.__species)
    
    # Below is how you create a private method
    def __correct_name(self):
        self.__name = self.__name.upper()



a = Animal('Dog', 'K9')
a.display()
```
