## Exp-8-Record-THRESHOLDING
## NAME : Dhanappriya S
## REG NO :212224230056

# Aim:
To implement and compare image segmentation using Global Thresholding, Adaptive Thresholding, and Otsu's Method in Python using OpenCV.

# Procedure:
1. **Import Libraries:** Import `cv2`, `numpy`, and `matplotlib.pyplot`.
2. **Load and Preprocess Image:** Read the input image using `cv2.imread()` and convert it into a grayscale image using `cv2.cvtColor()` with `cv2.COLOR_BGR2GRAY`.
3. **Apply Global Thresholding:** Use `cv2.threshold()` with a fixed threshold value (e.g., 127) and `cv2.THRESH_BINARY` to segment the grayscale image.
4. **Apply Adaptive Thresholding:** Use `cv2.adaptiveThreshold()` with `cv2.ADAPTIVE_THRESH_GAUSSIAN_C` to dynamically calculate threshold values for smaller regions of the image.
5. **Apply Otsu's Method:** Use `cv2.threshold()` combining `cv2.THRESH_BINARY + cv2.THRESH_OTSU` to automatically determine the optimal global threshold value from the image histogram.
6. **Display Results:** Plot the original image alongside the three thresholded outputs in a 2×2 grid using `matplotlib.pyplot.subplot()` and `imshow()`.

# Code:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Read the image and convert to grayscale
image = cv2.imread('photo.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)



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
# Output:

<img width="747" height="295" alt="image" src="https://github.com/user-attachments/assets/881439ed-5806-4a71-a5f3-1fdfe48c0362" />

<img width="773" height="600" alt="image" src="https://github.com/user-attachments/assets/00859a92-4152-43b2-ac46-2bd0fad7e2fc" />


# Result:
Thus to implement and compare image segmentation using Global Thresholding, Adaptive Thresholding, and Otsu's Method in Python using OpenCV was verified successfully.



