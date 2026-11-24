# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create a blank image using NumPy.

### Step 3:

Insert text onto the image using OpenCV's text drawing function.

### Step 4:

Display the original image.

### Step 5:

Create a structuring element (kernel) of suitable size.

### Step 6: Image Erosion

- Apply the erosion operation using the created kernel.
- Remove pixels from the boundaries of foreground objects.
- Display the eroded image.

### Step 7: Image Dilation

- Apply the dilation operation using the same kernel.
- Add pixels to the boundaries of foreground objects.
- Display the dilated image.

### Step 8:

Compare the original, eroded, and dilated images.

## Program

## Developed By
# Name: Vijiyalakshmi A
# Register No: 212225240185

```p

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load input image
img = cv2.imread('butterfly.jpg')

if img is None:
    print("Image not found")
else:
    # Step 2: Convert image into grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

    # Step 3: Convert into binary image
    ret, binary = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

    # Step 4: Create structuring element
    kernel = np.ones((5, 5), np.uint8)

    # Step 5: Apply Erosion
    erosion = cv2.erode(binary, kernel, iterations=1)

    # Step 6: Apply Dilation
    dilation = cv2.dilate(binary, kernel, iterations=1)

    # Step 7: Display images
    plt.figure(figsize=(12, 5))

    plt.subplot(1, 3, 1)
    plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
    plt.title('Original Image')
    plt.axis('off')

    plt.subplot(1, 3, 2)
    plt.imshow(erosion, cmap='gray')
    plt.title('Eroded Image')
    plt.axis('off')

    plt.subplot(1, 3, 3)
    plt.imshow(dilation, cmap='gray')
    plt.title('Dilated Image')
    plt.axis('off')

    plt.tight_layout()
    plt.show()

```

## Output

### Original Image

- A text image containing characters is displayed.
- The image serves as the input for morphological processing.

<img width="327" height="500" alt="image" src="https://github.com/user-attachments/assets/e529a7fb-e894-4af1-9f55-5abc52a5b118" />


### Erosion

- Original image is displayed.
- Eroded image is displayed.
- The thickness of the characters is reduced.
- Object boundaries shrink inward.

<img width="327" height="500" alt="image" src="https://github.com/user-attachments/assets/b72c5215-0563-4f91-880f-dd25325bcf2e" /><img width="332" height="497" alt="image" src="https://github.com/user-attachments/assets/d9226b78-22e4-4d81-abf5-d3234860a41a" />


### Dilation

- Original image is displayed.
- Dilated image is displayed.
- The thickness of the characters increases.
- Object boundaries expand outward.

<img width="327" height="500" alt="image" src="https://github.com/user-attachments/assets/547211a5-c246-4d83-a377-8f8924a0bc5b" /><img width="290" height="507" alt="image" src="https://github.com/user-attachments/assets/5a7738d3-7bfb-411f-935b-c781ede6186d" />


## Result

Thus, the morphological operations **Erosion** and **Dilation** are successfully implemented using OpenCV.
