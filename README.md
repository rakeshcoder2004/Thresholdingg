# EX NO-8
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
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

## Program
```
Developed By :Rakesh V
Register Number : 212222110036
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```PY
image = cv2.imread('zebra.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('zebra.jpg',0)
```
### Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```PY
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

![image](https://github.com/rakeshcoder2004/Thresholdingg/assets/121490890/4273e827-36ba-4e02-b05d-52258835e7fe)


### Global Thresholding

![image](https://github.com/rakeshcoder2004/Thresholdingg/assets/121490890/0552250e-b8d6-49c3-bd17-d75213a5d9d2)


### Adaptive Thresholding

![image](https://github.com/rakeshcoder2004/Thresholdingg/assets/121490890/1d0fa67d-14eb-4fb4-b53e-e7407f0b341d)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/rakeshcoder2004/Thresholdingg/assets/121490890/a4ed710c-c2d1-4d88-85c1-f0f5961c6109)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
