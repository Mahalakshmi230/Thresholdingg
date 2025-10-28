# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.
### Step2:
<br>
Read the image and convert to grayscale
### Step3:
<br>
Use global thresholding to segment the image.
### Step4:
<br>
Use Adaptive thresholding to segment the image.
### Step5:
<br>
Use Otsu's method to segment the image and display the results.

## Program

### Name: Mahalakshmi R
### Regno: 212223230116

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt


# Read the Image and convert to grayscale

image = cv2.imread(r"C:\Users\admin\OneDrive\Desktop\cat.jpeg")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')


# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
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
<img width="327" height="206" alt="Screenshot 2025-10-28 215826" src="https://github.com/user-attachments/assets/35cc03bb-20c4-4e30-965c-5ecc98623ce6" />


### Global Thresholding
<img width="324" height="205" alt="Screenshot 2025-10-28 215834" src="https://github.com/user-attachments/assets/bd0d4324-ee7e-4a6f-ba40-2a91b2722825" />


### Adaptive Thresholding
<img width="333" height="221" alt="Screenshot 2025-10-28 215841" src="https://github.com/user-attachments/assets/4c3e9f7e-c385-431c-a691-7a3a4650883b" />

### Optimum Global Thesholding using Otsu's Method
<img width="341" height="218" alt="Screenshot 2025-10-28 215848" src="https://github.com/user-attachments/assets/191582f2-857e-44f7-9210-a79973dcf1a4" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
