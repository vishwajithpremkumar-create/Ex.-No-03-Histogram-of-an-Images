# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** VISHWAJITH P 

**Register Number:** 212225220122

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('vishwa.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="497" height="556" alt="image" src="https://github.com/user-attachments/assets/c89481e3-c2c3-454e-a007-e405637adc60" />

### Input Grayscale Image Range
<img width="817" height="550" alt="image" src="https://github.com/user-attachments/assets/8dcb0d1b-c8ed-4bb0-8a51-80ac627292f6" />


### Input Grayscale Image Equalized Histogram
<img width="768" height="538" alt="image" src="https://github.com/user-attachments/assets/a5d35c7f-3f23-4be5-9bcb-0cd3e2f13c82" />

### Histogram of Grayscale Image and Color Image Channels

### Original Image
<img width="456" height="572" alt="image" src="https://github.com/user-attachments/assets/a45e7869-6463-4e67-a635-2f6fd0fbc00b" />


### Equalized Image

<img width="482" height="542" alt="image" src="https://github.com/user-attachments/assets/1f1382a3-c108-4a75-8f95-58491e923ee6" />

### Equalized Histogram
<img width="767" height="542" alt="image" src="https://github.com/user-attachments/assets/ddf9594a-268e-476c-bf1f-f2b5794b6232" />

### Final Output of Original Image and Equalized 
<img width="826" height="312" alt="image" src="https://github.com/user-attachments/assets/d1b3535e-c203-4dc4-8b85-ecc14bb0e485" />



### Final Output of Original Image and its Histogram Equalized
<img width="836" height="282" alt="image" src="https://github.com/user-attachments/assets/5c2f3e37-7520-4958-8368-ca7b47cbd82d" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
