# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load an image.Convert the input color image to grayscale using OpenCV’s cv2.cvtColor function.
Use matplotlib to visualize the grayscale image.

### Step2:
Apply global thresholding using cv2.threshold with a threshold value of 127.
Convert all pixels above 127 to white (255), and those below to black (0).
Display the resulting binary image.

### Step3:
Apply adaptive Gaussian thresholding using cv2.adaptiveThreshold.
The threshold value is calculated for small regions of the image.
Gaussian-weighted sum of neighborhood pixel values is used.
Display the resulting binary image.


### Step4:
Apply Otsu's thresholding using cv2.threshold with an automatic threshold calculated by minimizing the within-class variance.
Convert the image into a binary format using this optimal threshold.
Display the resulting binary image.
### Step5:
Visualize each stage:
Grayscale image
Global thresholded image
Adaptive Gaussian thresholded image
Otsu's thresholded image

## Program

```
Developed by : Prajin S
Register Number : 212223230151
```
### Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




### Read the Image and convert to grayscale
```python
image = cv2.imread('cow.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```



### Use Global thresholding to segment the image
```python
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```



### Use Adaptive thresholding to segment the image
```python
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```



### Use Otsu's method to segment the image 
```python
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```

## Output

### Original Image
![image](https://github.com/user-attachments/assets/ff5eaa02-074d-4f6d-8275-6a649aa841c1)


### Global Thresholding
![image](https://github.com/user-attachments/assets/004f6fbe-5be0-45bb-a612-dad1fe43745f)

### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/b89b9711-97a4-480b-b23f-f758db3b613d)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/cee1204e-1abf-4f19-b9f9-2b332725bb6d)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
