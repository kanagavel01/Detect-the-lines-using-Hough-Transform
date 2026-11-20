#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections


##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

###  Step 2: Read the Image

###  Step 3: Convert to Grayscale

###  Step 4: Display Images

###  Step 5: Thresholding

###  Step 6: Region of Interest (ROI)

### Step 7: Edge Detection (Canny)

###  Step 8: Gaussian Blur

###  Step 9: Hough Transform

### Step 10: Lane Detection Logic

---

## Program:

##  Developed By

* **Name:** Kanagavel R
* **Register No:** 212223040085

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('me.jpg')  # Replace 'image.jpg' with your image path
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
if line is not None:
    x1, y1, x2, y2 = line.flatten()  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 10)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```

## Output

* Original image

  <img width="360" height="510" alt="image" src="https://github.com/user-attachments/assets/603e7454-0926-4b3b-8446-1063fdf0e69d" />

* Grayscale image

  <img width="360" height="501" alt="image" src="https://github.com/user-attachments/assets/8beab7c4-5f14-4f9d-b59a-22c8c457a58c" />

* Canny Edge Detector

<img width="360" height="501" alt="image" src="https://github.com/user-attachments/assets/a13bf5f5-e7e1-4da4-b33f-33850f304801" />

* Result of Hough Transform

<img width="370" height="505" alt="image" src="https://github.com/user-attachments/assets/2f695954-efd5-44a9-a959-f361fd47a1b9" />

---


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
