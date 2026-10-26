# Histogram-of-an-images

## Name : Harisankar.S
## Reg no: 212224240051

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


```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.ylim(0,40000)
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
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');
plt.ylim(0,40000)
plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.ylim(0,40000)
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.ylim(0,40000)
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
plt.ylim(0,40000)
```

## Output

### Input Grayscale Image

<img width="379" height="434" alt="download" src="https://github.com/user-attachments/assets/8c0f4384-fbf2-471e-ab8e-da535689f7a1" />



### Input Grayscale Image Range

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/957f81a1-c372-48fb-979f-689ab57dad22" />


### Input Grayscale Image Equalized Histogram

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/4a36f8fb-a81a-4f13-a984-a204ef25f809" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="379" height="434" alt="download" src="https://github.com/user-attachments/assets/b2635568-76fc-4a38-a844-0c671f29db44" />



### Equalized Image

<img width="379" height="434" alt="download" src="https://github.com/user-attachments/assets/1fe50844-4aaa-4ab6-b8ae-be86611ef370" />



### Equalized Histogram
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/8e7c7f3a-e76c-4b14-8f0d-7048f8b5a2e7" />



### Final Output of Original Image and Equalized 
<img width="1208" height="414" alt="download" src="https://github.com/user-attachments/assets/7bc80055-f851-4f92-bc4e-30f96e078042" />



### Final Output of Original Image and its Histogram Equalized
<img width="1246" height="372" alt="download" src="https://github.com/user-attachments/assets/c277d5c3-1f37-4890-b25b-6494a9f302e1" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.

