# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

## Step1:
Load the necessary packages.

## Step2:
Read the Image and convert to grayscale.

## Step3:
Use Global thresholding to segment the image.

## Step4:
Use Adaptive thresholding to segment the image.

## Step5:
Use Otsu's method to segment the image and display the results.

## Program

```




# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('bird.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('bird.jpg',0)

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

![436937647-c9d8ff96-a1dd-4133-b107-10cb6930af74](https://github.com/user-attachments/assets/79557487-2b78-4adb-9dca-1a5a9f971e0b)


### Global Thresholding
![436937708-0e183e51-2a0f-43a9-aae6-227deb72bbf5](https://github.com/user-attachments/assets/247c38f5-0ec7-472e-84c0-3c5c9e34060e) ![436937747-7e6edc1c-5046-4693-9618-59aa6346aa49](https://github.com/user-attachments/assets/2717a97f-85eb-4b1c-abb1-de76b69fd40c)


### Adaptive Thresholding

![436938166-7e660bdc-89ad-403c-9e30-4bd2b268b0f3](https://github.com/user-attachments/assets/64292977-efb6-4bd5-ae37-055b3aba52d2)


### Optimum Global Thesholding using Otsu's Method

![436938007-0809d08b-a00e-414b-8fe5-faa3c8243f34](https://github.com/user-attachments/assets/8c0c3409-a4f3-492d-be7a-c1c40b56b706)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
