```py
import numpy as np

# Create a vector with rand nums from 5-15
arr_rand = np.random.randint(5, 15, 4)

# This will return an array of true and false
arr_rand_bool = arr_rand > 10

# Use the array of bools above to filter the array
print(arr_rand[arr_rand_bool])
```
