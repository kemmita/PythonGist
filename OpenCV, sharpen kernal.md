```py
import numpy as np
import matplotlib.pyplot as plt
import cv2

def sharpen_image(img):
    sharp_kernal = np.array([[0,-1,0],
                        [-1,5,-1],
                        [0,-1,0]])
    return cv2.filter2D(img,-1,sharp_kernal)
    
# read in image and convert to gray scale
i = cv2.imread('test_imgs/3.jpg')
i_gray = cv2.cvtColor(i, cv2.COLOR_BGR2GRAY)
plt.imshow(i_gray)

s_i = sharpen_image(i_gray)
plt.imshow(s_i)
```
