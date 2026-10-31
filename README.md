## EXP-3-Record-Histogram-processing-Completion-requirements--212224230284

### Name : SWETHA K
### REGISTER NUMBER : 212224230284
### EXPERIMENT : Record-Histogram processing

## Aim

To calculate and visualize the frequency distribution of pixel intensity values ranging from 0 to 255 in grayscale and color images. Also, to implement histogram equalization using OpenCV in Python to improve image contrast and enhance its visual appearance.

## Software Required

Anaconda - Python 3.7

OpenCV

NumPy

Matplotlib

## Algorithm

Step 1: Import the required libraries, including OpenCV, NumPy, and Matplotlib.

Step 2: Read the grayscale and color images using the cv2.imread() function.

Step 3: Display the input images using Matplotlib's imshow() function.

Step 4: Calculate the grayscale image histogram using cv2.calcHist() and determine the frequency of each pixel intensity.

Step 5: Extract the Blue, Green, and Red channels from the color image and calculate their respective histograms.

Step 6: Apply histogram equalization to the grayscale image using cv2.equalizeHist().

Step 7: Convert the color image into HSV color space and apply histogram equalization to the Value channel.

Step 8: Display the original and equalized images along with their corresponding histograms for comparison.

## Program 

Developed By: SWETHA K

Register Number: 212224230284

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r'C:\Users\admin\Downloads\my photo dipt.jpeg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread(r'C:\Users\admin\Downloads\my photo dipt.jpeg', cv2.IMREAD_COLOR)

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

## Input Grayscale Image

<img width="515" height="575" alt="image" src="https://github.com/user-attachments/assets/8f08ca34-30fd-43cb-a0e0-b6a0cb6d840c" />

## Input Grayscale Image Range

<img width="810" height="570" alt="image" src="https://github.com/user-attachments/assets/d28b1c54-7749-4768-8cf8-04c45442f936" />

## Input Grayscale Image Equalized Histogram

<img width="817" height="538" alt="image" src="https://github.com/user-attachments/assets/b224f32c-fb97-4bea-8040-685912d7e485" />

## Histogram of Grayscale Image and Color Image Channels

## Original Image

<img width="495" height="565" alt="image" src="https://github.com/user-attachments/assets/410cf4bb-41fb-4798-a02d-7083d6876f40" />

## Equalized Image

<img width="515" height="560" alt="image" src="https://github.com/user-attachments/assets/c26a5d67-942a-49fd-b482-499c84e66b7a" />

## Equalized Histogram

<img width="877" height="557" alt="image" src="https://github.com/user-attachments/assets/ad6efd37-93ad-4cd1-ad9d-2571d01a370b" />

## Final Output of Original Image and Equalized

<img width="932" height="325" alt="image" src="https://github.com/user-attachments/assets/a6e0ed71-662d-4c88-919d-4df84e4b2d69" />

## Final Output of Original Image and its Histogram Equalized


<img width="923" height="361" alt="image" src="https://github.com/user-attachments/assets/3fc9f84d-d87d-4ffb-b9fe-94c00e286647" />


## Result
Thus, the histograms of grayscale and color images were successfully generated, and histogram equalization was performed using OpenCV. The contrast and visual appearance of the images were enhanced, and the results were displayed for comparison.
