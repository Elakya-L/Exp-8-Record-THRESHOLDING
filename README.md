# Exp-8-Record-THRESHOLDING

## Name: ELAKYA L

## Reg No: 212225230066

## Aim

To perform image thresholding using OpenCV and Python for segmenting an image using Global Thresholding, Adaptive Thresholding, and Otsu's Method.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

Step 1 Import all the necessary modules for the program.

Step 2 Read an image using the `cv2.imread()` function and convert the image into grayscale using `cv2.cvtColor()`.

Step 3 Apply Global Thresholding using `cv2.threshold()` with a threshold value of 127.

Step 4 Apply Adaptive Thresholding using `cv2.adaptiveThreshold()` with the Gaussian adaptive method.

Step 5 Apply Otsu's Thresholding using `cv2.threshold()` with `cv2.THRESH_OTSU` to determine the optimal threshold value automatically.

Step 6 Display the original image along with the Global Thresholding, Adaptive Thresholding, and Otsu's Method results using Matplotlib.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('me.jpeg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(
    gray_image, 127, 255, cv2.THRESH_BINARY
)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(
    gray_image,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```

## Output

**Global Thresholding**

<img width="166" height="182" alt="image" src="https://github.com/user-attachments/assets/82ff2b2d-f9c8-4a83-a085-5b4eca71e6ed" />

**Adaptive Thresholding**

<img width="204" height="202" alt="image" src="https://github.com/user-attachments/assets/272b4eac-06ea-440d-8ab4-163b34292a9c" />

**Otsu's Method**

<img width="155" height="193" alt="image" src="https://github.com/user-attachments/assets/489d5a8e-49da-4e2b-8a6c-82ea73acea83" />

## Result

Thus, the image thresholding experiment was performed successfully using OpenCV and Python. The image was segmented using Global Thresholding, Adaptive Thresholding, and Otsu's Method, and the results were displayed successfully.
