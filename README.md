# Exp-8  Thresholding

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV

## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

### Program
#### NAME : KAMALESHWAR KV
#### REG NO : 212223240063

#### Step 1: Import the necessary libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
#### Step 2: Read the image and convert to grayscale
```
image = cv2.imread('Qn8_thresholding.tif')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```

#### Step 3: dispay the original image
```
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
<img width="447" height="375" alt="image" src="https://github.com/user-attachments/assets/ff30913d-566f-4f9b-99b3-02d6fafb3f7b" />

#### Step 4: Use Global Thresholding to segment the image
```
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```

#### Step 5: Use Adaptive Thresholding to segment the image

```
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```

#### Step 6: Use Otsu's method to segment the image

```
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
#### Global Thresholding
<img width="470" height="354" alt="image" src="https://github.com/user-attachments/assets/9dbc1c94-1a3a-47a3-ae71-4078f089c022" />


#### Adaptive Thresholding
<img width="366" height="374" alt="image" src="https://github.com/user-attachments/assets/26b6c7c5-beed-433a-8206-b9c119c3a899" />


#### Otsu's Method

<img width="377" height="362" alt="image" src="https://github.com/user-attachments/assets/c3d90977-b541-4e55-9370-0d68a6d805d4" />

## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
