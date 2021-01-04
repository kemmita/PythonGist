1. In C# if we want to pass functions to a nother function we would need to create a delegate, with Python it is a bit easier with first class functions.
```py
def divide(a, b):
    return a / b


def multiply(a, b):
    return a * b


# This function takes in a first class function, meaning we can now pass any type
# of calculation function to this function to be returned, for example, multiply, divide, etc...
def calculate(a, b, calc_function):
    return calc_function(a, b)


# Here we call the function and pass it two udf divide and multiply and with the third
# example, we use a lambda
calculation_one = calculate(10, 3, divide)
calculation_two = calculate(10, 3, multiply)
calculation_three = calculate(10, 3, lambda a, b: a**2 * b**2)

print(calculation_one)
print(calculation_two)
print(calculation_three)
```
