# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
### Developed By   : THAMIZH KUMARAN S
### Register Number: 212223240166


### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("img0.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

iv)Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![Screenshot 2025-05-06 134207](https://github.com/user-attachments/assets/b0086046-c8ce-41da-a7ad-1b03a5b61748)



ii)Using Weighted Averaging Filter

![Screenshot 2025-05-06 134214](https://github.com/user-attachments/assets/67b3d1f3-1984-4c74-a4a8-616ff834a81b)



iii)Using Gaussian Filter

![Screenshot 2025-05-06 134221](https://github.com/user-attachments/assets/861a5056-1abb-4b44-a0a7-45bbfef01c26)


iv) Using Median Filter

![Screenshot 2025-05-06 134229](https://github.com/user-attachments/assets/dc66b761-1472-4e64-bc73-3ecdd7a73b66)



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

![Screenshot 2025-05-06 134238](https://github.com/user-attachments/assets/69c92504-23b6-4d35-b7ef-59724427556d)


ii) Using Laplacian Operator

![Screenshot 2025-05-06 134244](https://github.com/user-attachments/assets/e65f5ad2-547a-4d8f-8159-0552abcf89fd)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
