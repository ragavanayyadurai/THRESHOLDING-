# EX-08 THRESHOLDING
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
DEVELOPED BY: Ragavendran A
REGISTER NO: 212222230114
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("hack.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("hack.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![Screenshot 2024-04-10 110528](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/a9c102be-54ca-4f2d-ad4e-567162cc8c02)
### Global Thresholding
![Screenshot 2024-04-10 110614](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/3c733b26-f580-49d2-968b-34df5611d90d)
![Screenshot 2024-04-10 110637](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/44dc24ec-d24b-4aa9-ae2d-a29298d90dc3)
![Screenshot 2024-04-10 110658](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/44c86e72-2d4f-4f45-9d84-a5936098ed92)
![Screenshot 2024-04-10 110733](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/4ae971a0-643c-41e6-aef9-52a9f1878541)
![Screenshot 2024-04-10 110759](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/7add88a4-b627-4d62-9532-c05d20f34b85)
### Adaptive Thresholding
![Screenshot 2024-04-10 110819](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/8cc2ca6c-96fa-48e4-834f-0c904e946685)
![Screenshot 2024-04-10 110839](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/dfc2efad-cc44-4677-8f92-98f91c242e41)
### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110902](https://github.com/ragavanayyadurai/THRESHOLDING-/assets/118749557/01a14252-aa3d-41b9-8e53-f20a1594ada3)
## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
