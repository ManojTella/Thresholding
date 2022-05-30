# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required packages
<br>

### Step2:
Import the image to operate on.
<br>

### Step3:
Convert the image to grayscale image.
<br>

### Step4:
Apply threshold operators on the image.
<br>

### Step5:
Display the output.
<br>

## Program
```python
# Devleoped by:- Manoj Guna Sundar Tella.
# Registration number:- 212221240026.
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("parrot.jpeg")







# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)


# Use Global thresholding to segment the image


ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)





# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]




# Use Otsu's method to segment the image 
ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()


cv2.imshow("Otsu method",th3)



```
## Output

### Original Image
![img1](https://user-images.githubusercontent.com/94883876/170659350-72f7be25-bd2f-42f7-8f9e-8ca923833c28.jpg)

![img2](https://user-images.githubusercontent.com/94883876/170661135-9e786cf7-ca0e-456a-814d-2d45927306f8.jpg)


<br>
<br>

### Global Thresholding
![img3](https://user-images.githubusercontent.com/94883876/170659660-16bab5ff-6853-46d6-8fd0-be1fbd36ac76.jpg)
![img4](https://user-images.githubusercontent.com/94883876/170659775-297ba570-a5aa-45df-98cf-6707aca17b6d.jpg)
![img5](https://user-images.githubusercontent.com/94883876/170659869-cdaca946-f013-40bb-91cd-9c9ee0070ee4.jpg)

### Adaptive Thresholding
![img6](https://user-images.githubusercontent.com/94883876/170659912-a90d7af0-7171-4e31-83eb-8d764230ed93.jpg)

<br>
<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
![img7](https://user-images.githubusercontent.com/94883876/170659945-83a260d2-60b5-4a45-a939-68e60738e1e8.jpg)

<br>
<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

