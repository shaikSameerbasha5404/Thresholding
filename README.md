# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Import required packages

### Step2:
Import the image to operate on.

### Step3:
Convert the image to grayscale image.

### Step4:
Apply threshold operators on the image.

### Step5:
Display the output.


## Program

```python
# Devleoped by:- sk sameer basha
# Registration number:- 212222240093
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("buggati.jpg")







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
![Screenshot from 2023-04-26 11-52-01](https://user-images.githubusercontent.com/118707756/235286711-8bf0263a-3919-4c5e-aeb2-fc864f65d62f.png)
![Screenshot from 2023-04-26 11-51-46](https://user-images.githubusercontent.com/118707756/235286707-8ee53d45-704f-469b-a3c9-8360ea76aa84.png)

### Global Thresholding
![Screenshot from 2023-04-26 11-51-46](https://user-images.githubusercontent.com/118707756/235286993-0ed13ec4-198e-4259-9678-ee6e7412ac2e.png)
![Screenshot from 2023-04-26 11-51-32](https://user-images.githubusercontent.com/118707756/235286996-09b7e272-8afe-4490-990d-f93d13c8f324.png)


### Adaptive Thresholding
![Screenshot from 2023-04-26 11-50-59](https://user-images.githubusercontent.com/118707756/235287015-20d5910a-e6d3-4a37-95f6-fbc42b9d817a.png)

![Screenshot from 2023-04-26 11-50-37](https://user-images.githubusercontent.com/118707756/235287021-3b09d1bc-6384-4c8f-832e-288ec792986e.png)

### Optimum Global Thesholding using Otsu's Method
![Screenshot from 2023-04-26 11-50-18](https://user-images.githubusercontent.com/118707756/235287031-9f8f2e11-0801-4af3-aabb-99392f30271c.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

