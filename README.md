# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
### Name: Priyadharshini S

### Register No: 212225230218
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('parrot.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
```
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
```
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

---

##  Output
<img width="562" height="317" alt="Screenshot 2026-10-27 091223" src="https://github.com/user-attachments/assets/87692b33-e855-4e71-bbf6-83eec1c8c659" />
<img width="567" height="416" alt="Screenshot 2026-10-27 091312" src="https://github.com/user-attachments/assets/110eb684-5fe3-40a8-ba27-629793e4abd0" />
<img width="540" height="325" alt="Screenshot 2026-10-27 091330" src="https://github.com/user-attachments/assets/7e8fc772-491c-4962-87df-620a6c6ef62f" />
<img width="560" height="192" alt="Screenshot 2026-10-27 091404" src="https://github.com/user-attachments/assets/5a31cdaa-df8d-4fee-89a3-c55dd0701585" />
<img width="978" height="747" alt="Screenshot 2026-10-27 091445" src="https://github.com/user-attachments/assets/95e5451e-b865-4656-8444-328a1769bfba" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
