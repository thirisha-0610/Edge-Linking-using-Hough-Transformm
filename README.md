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
<img width="378" height="455" alt="495634597-0085386f-baf6-436f-8d81-d9db0802ef87" src="https://github.com/user-attachments/assets/2be8dd56-a4e5-4c2d-96dd-6c9a8368db6d" />

<img width="358" height="444" alt="495634699-ac7b8dee-c34e-46b2-9029-6b909b26cd24" src="https://github.com/user-attachments/assets/25489deb-933f-4291-bc4a-0cb7bcc2f5c3" />


### Canny Edge detector output

<img width="343" height="448" alt="495634806-27a0323c-b554-40cd-8104-bb6d0322ed43" src="https://github.com/user-attachments/assets/3043d6f9-ece8-4ef1-b7e1-ea2f77a4918c" />

### Display the result of Hough transform

<img width="381" height="453" alt="495634922-4a79ec95-e8f3-4bc5-9c7d-97a7d5997363" src="https://github.com/user-attachments/assets/fe8820ff-5701-41fa-bf4e-231f7514d4bf" />

### RESULT:
Thus the program for Edge-Linking-using-Hough-Transform was executed successfully.
