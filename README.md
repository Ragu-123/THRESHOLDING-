# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image.
<br>

### Step6:
Display the results.
<br>

## Program
```
Developed by: RAGUNATH R
Register number :212222240081
```
# Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale
```python
image=cv2.imread("butterfly.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("butterfly.jpg",0)
```



# Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Use Otsu's method to segment the image 
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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
<br>

![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/b61f4000-5d35-44ec-add4-e3aaf14eef04)


<br>


### Global Thresholding
<br>

![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/55f3ad69-b0f0-41ec-8ce7-bb75ab367a1a)
![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/d55314f5-1a54-445d-af36-6d0b6b06365e)
![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/15a27993-da7b-4f8a-a6c0-267a589677f5)






<br>


### Adaptive Thresholding
<br>

![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/1b9b54f6-4154-47bb-9a08-8ff1e85ecb7f)



<br>


### Optimum Global Thesholding using Otsu's Method
<br>

![image](https://github.com/Ragu-123/THRESHOLDING-/assets/113915622/49e21f42-40e1-4138-9e1e-d4bea412f351)



<br>



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
