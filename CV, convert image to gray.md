```py
import numpy as np
import matplotlib.pyplot as plt
import cv2

i = cv2.imread('test_imgs/3.jpg')
i_gray = cv2.cvtColor(i, cv2.COLOR_BGR2GRAY)
display_image_in_actual_size(i_gray)
```
