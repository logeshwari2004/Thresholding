# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.


## Program
```
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread("mashabear.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("mashabear.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![1](https://github.com/logeshwari2004/Thresholding/assets/94211349/49a793c7-ecd1-4e50-a7e0-3d7e84420772)

### Global Thresholding
![2](https://github.com/logeshwari2004/Thresholding/assets/94211349/73f7ece7-0b70-4d54-bb11-832a0dd6aedf)
![3](https://github.com/logeshwari2004/Thresholding/assets/94211349/0ab8e53b-72b4-4b58-80b6-22128a111746)
![4](https://github.com/logeshwari2004/Thresholding/assets/94211349/93307b09-7115-4304-a8c5-12a0ea462b91)
![5](https://github.com/logeshwari2004/Thresholding/assets/94211349/f6ff4232-4fca-4284-9732-aee7a2ba65a6)
![6](https://github.com/logeshwari2004/Thresholding/assets/94211349/ac165ef6-3b48-4479-9736-ea1bb1cf80f5)
### Adaptive Thresholding
![7](https://github.com/logeshwari2004/Thresholding/assets/94211349/cd2b574d-baca-4ee8-b748-d3e6ba8f1f6e)
![8](https://github.com/logeshwari2004/Thresholding/assets/94211349/90f52e0a-0b40-42ad-a211-a4069ce42df7)
### Optimum Global Thesholding using Otsu's Method
![9](https://github.com/logeshwari2004/Thresholding/assets/94211349/89798b85-298b-418a-b1e9-59b838b200f2)
## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

