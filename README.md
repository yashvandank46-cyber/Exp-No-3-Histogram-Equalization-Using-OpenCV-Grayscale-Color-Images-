# Histogram Equalization Using OpenCV (Grayscale & Color Images)

# NAME : YASHVANDAN K
# REG NO : 212225100060

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
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('pk.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 255]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('pk.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (30,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')


```


##  Output
<img width="455" height="537" alt="Screenshot 2026-10-29 110152" src="https://github.com/user-attachments/assets/0560fc41-8522-48b0-860e-2d9e0e0ab3fc" />
<img width="806" height="522" alt="Screenshot 2026-10-29 110220" src="https://github.com/user-attachments/assets/5f55779e-07db-4983-9822-18b5a93f81eb" />
<img width="762" height="530" alt="Screenshot 2026-10-29 110228" src="https://github.com/user-attachments/assets/3c6d73e2-e7f1-4f56-956d-f70a0f73707d" />
<img width="521" height="547" alt="Screenshot 2026-10-29 110236" src="https://github.com/user-attachments/assets/cbfedd75-045c-4d1c-a134-afd4db34c16c" />
<img width="465" height="536" alt="Screenshot 2026-10-29 110243" src="https://github.com/user-attachments/assets/e002c466-b7b5-437d-9e27-f4a7c6760bd7" />
<img width="767" height="525" alt="Screenshot 2026-10-29 110257" src="https://github.com/user-attachments/assets/7ed4cb17-1e34-4fca-9870-ef37c1220cde" />
<img width="1397" height="473" alt="Screenshot 2026-10-29 110307" src="https://github.com/user-attachments/assets/1043c00e-2bfa-4744-ad49-d670cc680f05" />
<img width="1387" height="407" alt="Screenshot 2026-10-29 110317" src="https://github.com/user-attachments/assets/74fb4408-6822-4599-8e20-0f25a1855b87" />




## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
