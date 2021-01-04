1. The class
```py
class Student:
    # Use the constructor to define instant variables that can be used by any function using self
    def __init__(self, age, name, level):
        self.age = age
        self.name = name
        self.level = level

    # Here is an instance method that can only be used once a new instance of the class has been instantiated.
    def student_bio(self):
        return print(f'{self.name} is {self.age} years old and is a {self.level}!')

    # Declare class wide variable, these variables can be used without the class being instantiated.
    Level_Types = ("Junior", "Freshman", "Sophomore", "Senior")

    @classmethod
    def level_gist(cls):
        return f'A first year student is typically refered to as {cls.Level_Types[1]}'

    @staticmethod
    def weekly_message():
        return 'This week we will have speaker x coming to visit our school!'
```
2. Using the class
```py
# First I would like to see the weekly message for students,
# this is not specific to any one student object and in fact uses
# no class fields, this is a static method call
print(Student.weekly_message())

# Now I would like to see what Level_Types are available to assign to a student.
print(Student.Level_Types)

# Next I would like to see the weekly message for students, this is not specific to any student, we call a class method
print(Student.level_gist())

# This is a static method that has access to no class properties.
print(Student.weekly_message())

# Now we want to create a student object that is unique to Sarah.
student = Student(19, 'Sarah', 'Junior')

# Now we call an instance method that exists only on Sarah at the moment.
print(student.student_bio())

```
