# Thresholding of Images
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
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

## PROGRAM:

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("image.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("image.jpg",0)

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
## OUTPUT:

### Original Image
![output](https://user-images.githubusercontent.com/94169913/170804197-03651e68-9602-4cad-97e5-8bf656b25ea2.png)
<br>

### Global Thresholding
![binary](https://user-images.githubusercontent.com/94169913/170804215-9ebf1488-48f6-41b6-9ec1-742318a55214.png)
<br>

![binaryinv](https://user-images.githubusercontent.com/94169913/170804220-4bcc4b01-3298-4e0b-89c8-4b5fa34f505f.png)
<br>

![tozero](https://user-images.githubusercontent.com/94169913/170804228-b31f47fc-85a4-4fa0-89f2-e28bf3466ebe.png)
<br>

![tozeroinv](https://user-images.githubusercontent.com/94169913/170804233-6760ca96-d7e5-4ab9-b22d-20b6dab7ee10.png)
<br>

![truncate](https://user-images.githubusercontent.com/94169913/170804241-3975793c-6bf2-4548-9751-42c49400cda7.png)
<br>

### Adaptive Thresholding
![atmean](https://user-images.githubusercontent.com/94169913/170804257-8db21a81-3783-461f-886e-240232844b43.png)
<br>

![atgauss](https://user-images.githubusercontent.com/94169913/170804270-0a8c86ca-04ce-4ab5-9d14-b81e692162c5.png)
<br>

### Optimum Global Thesholding using Otsu's Method
![otsu](https://user-images.githubusercontent.com/94169913/170804281-771feca2-1675-4491-8b00-3149140aba2e.png)

<br>


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

