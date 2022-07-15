```py
def model_validation(func):
    def wrapper(*args, **kwargs):
        if kwargs.get('my_arg', None) == 'p':
            raise Exception('bad')
        func(*args, **kwargs)

    return wrapper


@model_validation
def model_a_predict(my_arg):
    print(my_arg)


@model_validation
def model_b_predict(my_arg):
    print(my_arg)


model_a_predict(my_arg='a')
model_b_predict(my_arg='b')
model_b_predict(my_arg='p')
```
