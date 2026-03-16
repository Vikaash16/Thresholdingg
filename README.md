# THRESHOLDING
## DEVELOPED BY : Vikaash P
## REG NO : 212223240180
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.
## Program

```python
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread('VI.jpeg')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Original image

plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Use Global thresholding to segment the image

_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
## Output

### Original Image
<img width="303" height="204" alt="image" src="https://github.com/user-attachments/assets/5bee9ef4-89a2-49b8-90ac-3d38612ee7e7" />


### Global Thresholding
<img width="316" height="217" alt="image" src="https://github.com/user-attachments/assets/6ee0c0b8-c504-4fc4-8f33-5f8873ebd18a" />


### Adaptive Thresholding
<img width="319" height="205" alt="image" src="https://github.com/user-attachments/assets/75f266b4-0c0b-4a9c-836c-6ef9c22de499" />

### Optimum Global Thesholding using Otsu's Method
<img width="304" height="204" alt="image" src="https://github.com/user-attachments/assets/a02e1774-37bf-4e1b-9664-912f109208fa" />


## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

