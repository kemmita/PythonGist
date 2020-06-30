1. Using broadcasting we can set part or our entire array to a set value.
```py
import numpy as np

# all 4 elements of our array will now be set to 100.
arr_rand = np.random.randint(5, 15, 4)
arr_rand[0:4] = 100
print(arr_rand)
```
