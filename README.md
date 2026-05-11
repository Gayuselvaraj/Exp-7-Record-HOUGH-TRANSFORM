# Edge-Linking-using-Hough-Transformm
### Developed by:GAYATHRI S
### Register No:212224230073
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

### Program
### Developed by:GAYATHRI S
### Register No:212224230073
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('eagle.png')

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
## Output

### Input image and grayscale image

<img width="948" height="578" alt="image" src="https://github.com/user-attachments/assets/c98ca5e8-d52b-4f36-8b94-c54dee087afd" />


<img width="856" height="580" alt="image" src="https://github.com/user-attachments/assets/5151d090-093f-4102-b213-1e3529f12ad0" />




### Canny Edge detector output

<img width="787" height="601" alt="image" src="https://github.com/user-attachments/assets/0626e254-a087-45ad-b32f-fbf2ab4bebcc" />


### Display the result of Hough transform

<img width="802" height="623" alt="image" src="https://github.com/user-attachments/assets/4aa0c4a8-dab9-4773-8bde-e0304cd984ff" />


### Result
Thus the programs are executed successfully
