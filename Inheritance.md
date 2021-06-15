```py
class Animal(object):
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def display(self):
        self.__correct_name()
        print(self.name)
        print(self.species)

    def correct_name(self):
        self.name = self.name.upper()


class Dog(Animal):
    def __init__(self, name, species, breed):
        super().__init__(name, species)
        self.breed = breed

    def test_this(self):
        self.correct_name()
        print(self.breed, self.name, self.species)


d = Dog('Dog', 'K9', 'German Shepard')
d.test_this()
```
