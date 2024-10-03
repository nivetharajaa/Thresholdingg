![329453640-3a0d534c-8a11-48f1-8655-4866b7587c54](https://github.com/user-attachments/assets/e9bd9114-65b8-4700-a070-43aac0dceee0)# EX-08 THRESHOLDING
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
### NAME: Nivetha A
### REG NO:212222230101
```
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('cat.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cat.jpeg.jpg',0)

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

![329453443-896a5060-0d4a-4627-b8b0-d7c994026727-2](https://github.com/user-attachments/assets/aa9b223a-3e8b-4e10-9976-a638bdd38b4e)


### Global Thresholding

![329453547-1a03e9e5-b47c-4d5c-8ff1-eb5c4d8bb3ea-1](https://github.com/user-attachments/assets/5f59ab8a-9d56-4244-a286-9bf375381131)

![329453640-3a0d534c-8a11-48f1-8655-4866b7587c54](https://github.com/user-attachments/assets/b3ca8c27-d762-4ede-9c8f-82a86b05f123)

![329453839-c65b8a57-b438-4522-a1d1-6a20e36b93c6](https://github.com/user-attachments/assets/55b6a168-17d9-4a86-b94a-8aee5fcf7bda)

![329453979-dffff962-4142-4c08-abf8-d13db895829f](https://github.com/user-attachments/assets/459328a5-caee-4115-815e-b46ae9e02b45)

### Adaptive Thresholding
![329455799-a5829b2f-2ae8-4ccf-91e9-5859f1231a66](https://github.com/user-attachments/assets/68ddf30b-1daf-4f02-8add-a1c9b9982055)

![329455878-347cb803-cc31-4272-af0b-c2cad83c57bc](https://github.com/user-attachments/assets/3aa99ec8-89f8-4ea8-8ff9-e3f31f92e4d6)


### Optimum Global Thesholding using Otsu's Method

![329454117-962144c1-fd6a-4b60-bdc7-bda5b413236d](https://github.com/user-attachments/assets/ea22f909-ca01-4ebb-b42e-69b2a5f1db21)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
