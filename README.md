# EDGE-DETECTION
# Developed By:JEECIKASRINA M
# Reg no:2122232100015
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
# Program:
Developed By:JEECIKASRINA M

Reg no:212223100015
```
from google.colab import files
import cv2
import numpy as np
import matplotlib.pyplot as plt
import os
uploaded = files.upload()
filename = next(iter(uploaded))
print("Uploaded file:", filename)
image = cv2.imread(filename)
if image is None:
    raise ValueError(f" Image not found. Check if the file name '{filename}' is correct.")
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.figure(figsize=(10,10))

plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)
sobel_combined = cv2.magnitude(sobel_x, sobel_y)

plt.subplot(2,2,2)
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.subplot(2,2,3)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)

plt.subplot(2,2,4)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()




```

## Output:
# Original image:
<img width="638" height="463" alt="image" src="https://github.com/user-attachments/assets/d1177206-a3bd-4d53-ab46-dd633cb5108e" />

### SOBEL EDGE DETECTOR
<img width="652" height="446" alt="image" src="https://github.com/user-attachments/assets/2306b61a-f9d9-4fb2-aab9-b4bcb6a2f704" />


### LAPLACIAN EDGE DETECTOR
<img width="620" height="445" alt="image" src="https://github.com/user-attachments/assets/a2a1318e-8dd7-4b10-88d9-97ca08c355b9" />


### CANNY EDGE DETECTOR
<img width="637" height="447" alt="image" src="https://github.com/user-attachments/assets/a32eee01-2527-4771-8371-cb4e7ecd35cd" />

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
