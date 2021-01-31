```py
import numpy as np
import matplotlib.pyplot as plt
import cv2

img = cv2.imread('Computer-Vision-with-Python/DATA/00-puppy.jpg')

# Color images will show up initially as BGR and not RGB, we need to convert that.
fixed_img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(fixed_img)



```
