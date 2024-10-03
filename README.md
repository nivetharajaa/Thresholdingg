![329453443-896a5060-0d4a-4627-b8b0-d7c994026727](https://github.com/user-attachments/assets/3bd77ccd-1179-4f86-acc4-15256481dbe3)# THRESHOLDING
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
```
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2




# Read the Image and convert to grayscale

import numpy as np
import matplotlib.pyplot as plt
import cv2


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
![329453443-896a5060-0d4a-4627-b8b0-d7c994026727-1](https://github.com/user-attachments/assets/01ab3a6f-f35d-407d-adf9-618620470d5c)


### Global Thresholding

![329453547-1a03e9e5-b47c-4d5c-8ff1-eb5c4d8bb3ea-1](https://github.com/user-attachments/assets/924c45bd-8722-4c31-be96-53b1d5a71dfd)

### Adaptive Thresholding
![329455799-a5829b2f-2ae8-4ccf-91e9-5859f1231a66](https://github.com/user-attachments/assets/28eb6905-8bd8-4465-a9bf-824392ff27f7)


### Optimum Global Thesholding using Otsu's Method


![329454117-962144c1-fd6a-4b60-bdc7-bda5b413236d](https://github.com/user-attachments/assets/5e0d7665-85b5-469c-b192-f93d7bf8a625)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
