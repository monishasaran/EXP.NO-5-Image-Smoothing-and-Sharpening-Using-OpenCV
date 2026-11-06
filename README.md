# EXP.NO-5-Image-Smoothing-and-Sharpening-Using-OpenCV
# Aim
To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

# The program performs the following operations:
Read and display an input image

Apply Averaging filter

Apply Weighted Averaging filter

Apply Gaussian filter

Apply Median filter

Apply Laplacian sharpening using kernel

Apply Laplacian operator

Display all outputs for comparison

# Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image (e.g., image.jpg).

Step 3:
Convert the image from BGR to RGB format for display.

Step 4:
Apply Averaging Filter using cv2.blur().

Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

Step 7:
Apply Median Filter using cv2.medianBlur().

Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

Step 10:
Display all filtered images using a grid layout for comparison.

# Developed By
# Name: MONISHA S
# Register No: 212225040258

# CODE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('PHOTO.jpeg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.axis('off')

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray, cmap='gray')
plt.axis('off')

blur = cv2.GaussianBlur(gray, (5, 5), 0)
plt.imshow(blur, cmap='gray')
plt.axis('off')

edges = cv2.Canny(blur, 100, 200)
plt.imshow(edges, cmap='gray')
plt.axis('off')

kernel = np.ones((5, 5), np.uint8)
dilation = cv2.dilate(edges, kernel, iterations=1)
plt.imshow(dilation, cmap='gray')
plt.axis('off')

erosion = cv2.erode(edges, kernel, iterations=1)
plt.imshow(erosion, cmap='gray')
plt.axis('off')
```
# Output:
<img width="705" height="436" alt="image" src="https://github.com/user-attachments/assets/b08bcb2d-807f-4f17-84e3-b4dfb56a095b" />
<img width="517" height="332" alt="image" src="https://github.com/user-attachments/assets/4335d49e-5387-447e-b164-826a9fa7b789" />
<img width="498" height="322" alt="image" src="https://github.com/user-attachments/assets/05e98391-2353-4678-a02e-338e068f5aa0" />
<img width="700" height="441" alt="image" src="https://github.com/user-attachments/assets/63a5d904-3a52-493a-92c9-91d7a8481308" />

<img width="502" height="317" alt="image" src="https://github.com/user-attachments/assets/ce431fa7-dba6-4f97-9954-8143edeb1c79" />


<img width="496" height="317" alt="image" src="https://github.com/user-attachments/assets/0a276ef0-adfa-43f7-8fe6-d6fb5c065570" />







# Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
