1. To add a vector a<2, -3> b<4, 5> a+b is to 2i -3j + 4i + 5j. To solve, 2i + 4i = 6i and -3j + 5j = 2j = [6, 2]
```py
import numpy as np

a = np.array([2, -3])
b = np.array([4, 5])

print(a + b)
```

2. Scalar multiplication to a vector 2a - 3b would be to distribute the 2 across a and the -3 across b. Once that has been done, reapat the steps notated above.
```py
import numpy as np
a = np.array([2, -3])
b = np.array([4, 5])

print((2*a) - (3*b))
```

3. Scalar addition to a vector a<2, -3> + 5 = <i+5, j+5> = <7, 2>
```py
import numpy as np

a = np.array([2, -3])
b = np.array([4, 5])

print(5 + a)
```

4. Adding, subtracting and multiplication two vectors = ai+bi, ai-bi, ai*bi
```py
a = np.array([2, -3])
b = np.array([4, 5])

print(a + b) # = 2 + 4, -3 + 5 = <6, 2>
print(a - b) # = 2 - 4, -3 - 5 = <-2, -8>
print(a * b) # = 2 * 4, -3 * 5 = <8, -15>
```
