# Edge-Linking-using-Hough-Transformm
# NAME: THIRISHA A
# REG NO: 212223040228
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
# PROGRAM:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('dog cat.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
```

### Input image and grayscale image
<img width="376" height="366" alt="image" src="https://github.com/user-attachments/assets/2a33e70c-b47c-425b-8905-42068c9e6493" />

<img width="364" height="377" alt="image" src="https://github.com/user-attachments/assets/fe9cde63-bfd1-4568-9286-1268f2370bcf" />


### Canny Edge detector output

<img width="371" height="383" alt="image" src="https://github.com/user-attachments/assets/d1b7ec42-a7af-4ea7-a13f-622fb452902a" />

### Display the result of Hough transform
<img width="382" height="378" alt="image" src="https://github.com/user-attachments/assets/13a878c1-0899-4d48-91d3-890a548e8598" />

### RESULT:
Thus the program for Edge-Linking-using-Hough-Transform was executed successfully.
