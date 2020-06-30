```py
import numpy as np

# Create a 5x5 matrix with rand nums from 5-15
matrix_rand = np.random.randint(5, 15, (5, 5))
print(matrix_rand, "       sep       ")
# Access the first vector within the matrix
print(matrix_rand[0])
# Access the first scalar in the first vector within the matrix
print(matrix_rand[0, 0])
# Access the first 2 vectors in the matrix
print(matrix_rand[:2], "sep")
# Access the first 2 vectors in the matrix and only show the scalars within each vector starting at position 2
print(matrix_rand[:2, 2:])
```
