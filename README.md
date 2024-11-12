
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:
```
#Name:  SUDHIR KUMAR. R
#Reg No: 212223230221
```
## Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
## Create the Text using cv2.putText
```
# Read the color image
input_image_path = '/content/Screenshot 2024-11-12 220637.png'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200)  # you can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Perform opening
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)

# Perform closing
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)
```


## Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
```


## Use Opening operation
```
plt.subplot(2, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('on')
```



## Use Closing Operation
```
plt.subplot(2, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('on')

plt.show()

```
## Output:
### Display the input Image

![image](https://github.com/user-attachments/assets/fb2049ca-112c-45e7-885f-db8c6fc6ec57)

### Display the result of Opening

![image](https://github.com/user-attachments/assets/e682935a-4c92-4c77-a3f3-880fed1b9003)

### Display the result of Closing

![image](https://github.com/user-attachments/assets/467fb8f0-454f-4e0a-ad57-2257e8ff01b3)

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
