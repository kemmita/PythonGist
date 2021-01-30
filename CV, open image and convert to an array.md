```py
import numpy as np
import matplotlib.pyplot as plt
from PIL import Image

# Open image from disc
pic = Image.open('Computer-Vision-with-Python/DATA/00-puppy.jpg')

# Convert image to numpy array
pic_arr = np.asanyarray(pic)

pic_arr
```
