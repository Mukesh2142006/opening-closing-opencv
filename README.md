# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

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

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

## Developed By

**Name:** Mukesh B

**Register No:** 212223230128

```


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image in grayscale
image = cv2.imread("mukesh.jpeg", 0)

if image is None:
    print("Image not found!")
else:
    plt.imshow(image, cmap='gray')
    plt.title("Original Image")
    plt.axis("off")
    plt.show()


# Create structuring element
kernel = np.ones((5, 5), np.uint8)

# Perform Opening
opening = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display output
plt.imshow(opening, cmap='gray')
plt.title("Opening Image")
plt.axis("off")
plt.show()


# Create structuring element
kernel = np.ones((5, 5), np.uint8)

# Perform Closing
closing = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Display output
plt.imshow(closing, cmap='gray')
plt.title("Closing Image")
plt.axis("off")
plt.show()


```

## Output

### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.
<img width="308" height="323" alt="image" src="https://github.com/user-attachments/assets/f91d485f-0ca1-49b3-89bd-25c41b538e53" />


### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.
<img width="305" height="335" alt="image" src="https://github.com/user-attachments/assets/52b9c49d-caad-4cfb-9835-15c02ccfb286" />


### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.
<img width="302" height="326" alt="image" src="https://github.com/user-attachments/assets/80d4172e-bc03-4a9c-8527-a3f66decbf3d" />

## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
