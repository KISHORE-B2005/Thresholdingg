# THRESHOLDING
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
## Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
Developed By: KISHORE B
Reg.NO: 212222110020
```
```
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('GATE.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('GATE.jpg',0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

#Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
# Display the results

for i in range(0,9):
    plt.figure(figsize=(10,10))
  
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![car](https://github.com/user-attachments/assets/cdad146a-ff87-4b70-a818-0c4b1b2559c6)

### Gray Image
![image](https://github.com/user-attachments/assets/414033b3-30c4-40cf-8b73-7aa5da72a8aa)


### Global Thresholding
![image](https://github.com/user-attachments/assets/3d9922d7-6e19-4bb7-a433-b48cb53dd54a)
![image](https://github.com/user-attachments/assets/8070b1cb-20ec-4c17-ac5f-d7749cd4c693)
![image](https://github.com/user-attachments/assets/c0a8349f-0f97-4c0e-b36c-c8ac71d1f71a)
![image](https://github.com/user-attachments/assets/aedbb373-d521-4866-b38e-ef00c19eb927)
![image](https://github.com/user-attachments/assets/24fecac4-3669-47b5-aac3-10bd8aea1625)

### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/b0950fa7-2d78-4dd0-9e79-8b18d8d67b16)
![image](https://github.com/user-attachments/assets/95bac3cf-5661-4c95-a68c-06a61b6ac607)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/418f73e3-ce03-4930-8aeb-57f6bade146a)
## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
