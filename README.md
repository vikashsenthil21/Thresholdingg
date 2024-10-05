# Thresholding

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.


## Program

#### Name : Vikash s
#### Register no : 212222240115

### Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read and show the Original image
```
image = cv2.imread('tj.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```
### Output:

![Screenshot 2024-10-05 161656](https://github.com/user-attachments/assets/d29424f5-4bef-4006-a353-ed417640818a)

### Convert the image to grayscale
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![image](https://github.com/user-attachments/assets/9d0c3661-fb64-4702-8883-cce10cca9ab9)

### Use Global thresholding to segment the image
```
# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![image](https://github.com/user-attachments/assets/09529fed-8a65-4ba2-99c1-e7da4bf96eca)

### Use Adaptive thresholding to segment the image
```
# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![image](https://github.com/user-attachments/assets/19e89356-f1f0-4435-a765-276d121fedc2)

### Use Otsu's method to segment the image 
```
# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![image](https://github.com/user-attachments/assets/d46c703a-aecc-42c1-9598-847db0515e7a)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
