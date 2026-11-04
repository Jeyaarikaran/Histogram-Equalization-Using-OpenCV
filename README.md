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


### Developed By:
### Name: Jeyaarikaran.P

### Register No: 21224240064


## Program
```.py
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read Grayscale Image
img = cv2.imread(r'C:\Users\admin\Downloads\defender.png', cv2.IMREAD_GRAYSCALE)

# Display Original Grayscale Image
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Original Histogram
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')
plt.show()

# Histogram Equalization
img_eq = cv2.equalizeHist(img)

# Equalized Histogram
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

# Display Equalized Image
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

# Read Color Image
img = cv2.imread(r'C:\Users\admin\Downloads\defender.png', cv2.IMREAD_COLOR)

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Apply Histogram Equalization to V Channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display Equalized Color Image
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')
plt.show()

# Histogram of Equalized Color Image
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

# Compare Original and Equalized Color Images
plt.figure(figsize=(20, 10))

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')

plt.show()

# Compare Original and Equalized Histograms
plt.figure(figsize=(15, 4))

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image Histogram')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Image Histogram')

plt.show()
```

---

##  Output

#### Input Grayscale Image

<img width="843" height="447" alt="image" src="https://github.com/user-attachments/assets/51401faa-f449-498f-a783-a9a43a083c0d" />


### Input Grayscale Image Range

<img width="822" height="446" alt="image" src="https://github.com/user-attachments/assets/5d502d13-9098-45c3-9363-e41c960d8e0e" />

### Input Grayscale Image Equalized Histogram

<img width="877" height="445" alt="image" src="https://github.com/user-attachments/assets/124268af-97c5-4317-b7f0-7ed02f7b57d1" />


### Histogram of Grayscale Image and Color Image Channels

#### Original Image

<img width="836" height="447" alt="image" src="https://github.com/user-attachments/assets/0209fd45-e52c-4a65-a35b-ecc48049ee74" />

#### Equalized Image


<img width="871" height="471" alt="image" src="https://github.com/user-attachments/assets/c832ea43-fb87-4c5d-9567-34034d1672e8" />

### Equalized Histogram

<img width="860" height="466" alt="image" src="https://github.com/user-attachments/assets/4e908967-652b-4afc-bb79-9dee39a556b6" />

### Final Output of Original Image and Equalized

<img width="1140" height="333" alt="image" src="https://github.com/user-attachments/assets/52b2f79b-6e4e-47a6-bdec-e6ccde82c36c" />


### Final Output of Original Image and its Histogram Equalized

<img width="1142" height="320" alt="image" src="https://github.com/user-attachments/assets/48a65840-5dab-44ed-8de8-3af91dc824a1" />



## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
