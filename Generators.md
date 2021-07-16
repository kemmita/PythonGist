```py
def square_list(nums):
    result = []
    for i in nums:
        result.append(i**2)
    return result


print(square_list([1,2,3,4,5]))


def square_generator(nums):
    for i in nums:
        yield i ** 2


gen = square_generator([1,2,3,4,5])
for i in gen:
    print(i)
```
