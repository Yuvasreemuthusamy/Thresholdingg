# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the required libraries like OpenCV, NumPy, and Matplotlib.
<br>
### Step2:
Read the input image from the file and convert it to grayscale using OpenCV.
<br>
### Step3:
Apply different thresholding techniques:

Global thresholding (binary, binary inverse, truncate, to zero, to zero inverse). Otsu’s thresholding. Adaptive thresholding (mean, Gaussian).
<br>

### Step4:
Store the results of each thresholding operation in a list for easy visualization.
<br>

### Step5:
Display the original grayscale image and the thresholded images side by side using Matplotlib to compare results.
<br>
### Developed by: YUVA SREE M
### Register Number: 212223230251
## Program

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg")
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

ret, thresh_dipt1 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_BINARY)
ret, thresh_dipt2 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_BINARY_INV)
ret, thresh_dipt3 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_TOZERO)
ret, thresh_dipt4 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_TOZERO_INV)
ret, thresh_dipt5 = cv2.threshold(image_gray, 100, 255, cv2.THRESH_TRUNC)

ret, thresh_dipt6 = cv2.threshold(image_gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

thresh_dipt7 = cv2.adaptiveThreshold(image_gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
thresh_dipt8 = cv2.adaptiveThreshold(image_gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

titles = [
    "Gray Image", 
    "Threshold Image (Binary)", 
    "Threshold Image (Binary Inverse)", 
    "Threshold Image (To Zero)", 
    "Threshold Image (To Zero-Inverse)", 
    "Threshold Image (Truncate)", 
    "Otsu's Threshold", 
    "Adaptive Threshold (Mean)", 
    "Adaptive Threshold (Gaussian)"
]

images = [
    image_gray, thresh_dipt1, thresh_dipt2, thresh_dipt3, 
    thresh_dipt4, thresh_dipt5, thresh_dipt6, thresh_dipt7, thresh_dipt8
]

for i in range(9):
    plt.figure(figsize=(8, 8))
    plt.subplot(1, 2, 1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1, 2, 2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![image](https://github.com/user-attachments/assets/6d4c4244-01b7-4638-ad45-01e4ba482ff4)

### Global Thresholding
![image](https://github.com/user-attachments/assets/f15f86d0-ae4d-491a-aa10-7416b79b5017)

![image](https://github.com/user-attachments/assets/ddaca401-d3ba-447b-9f90-8c26a6fcb4e2)

![image](https://github.com/user-attachments/assets/16794c71-0ea5-49a1-be36-fa452f1365ef)

![image](https://github.com/user-attachments/assets/6b2646d4-3175-4bd0-9a56-38d5530d38f6)

![image](https://github.com/user-attachments/assets/3a266d37-a195-47ea-ab90-00d2004b4032)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/4e037087-4a86-4c25-9c9f-02b760af481d)

![image](https://github.com/user-attachments/assets/b340be5e-dee0-4d91-bb2f-0db0af3d9b1f)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/4b37b368-9ede-46ca-8eaf-c151bff73db7)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
