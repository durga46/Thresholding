# Thresholding of Images
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
Use Adaptive thresholding to segment the image
### Step5:
<br>
Use Otsu's method to segment the image.
### Step6::
<br>
Display the results.


## Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("porsche.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("porsche.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)",
"Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu",
       "Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,
thresh_img6,thresh_img7,thresh_img8]
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
![t1](https://user-images.githubusercontent.com/75235704/171362997-bef5b79c-3aff-4e25-a510-13d9e3653cd4.png)

<br>
<br>
<br>
<br>
<br>

### Global Thresholding
![t2](https://user-images.githubusercontent.com/75235704/171363099-4e50d158-36d9-40b9-bd1f-7ec9a0462347.png)
![t3](https://user-images.githubusercontent.com/75235704/171363269-71ea6073-64e1-4a7e-b5c2-4908c8bb974e.png)

![t4](https://user-images.githubusercontent.com/75235704/171363380-fa823abd-a198-4a95-b003-1295139465ff.png)

![t5](https://user-images.githubusercontent.com/75235704/171363398-cd11fd0a-b842-45eb-b840-dd04103ae771.png)
![t6](https://user-images.githubusercontent.com/75235704/171363425-d6a424bf-e3d6-4880-8abb-5fc9fc3da018.png)

<br>
<br>
<br>
<br>
<br>

### Adaptive Thresholding

![t7](https://user-images.githubusercontent.com/75235704/171363479-e0ba6b0b-d037-49ec-a2d6-a14a1cb1efac.png)
![t8](https://user-images.githubusercontent.com/75235704/171363497-e06247e1-2c38-4626-bfd6-69e07bb42dc6.png)

<br>
<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
![t9](https://user-images.githubusercontent.com/75235704/171363528-d5a71f64-3cd5-42fb-aec0-f68ae0467000.png)

<br>
<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

