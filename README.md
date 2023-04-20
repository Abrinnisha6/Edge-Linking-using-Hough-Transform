# Edge-Linking-using-Hough-Transform

## Aim:

To write a Python program to detect the lines using Hough Transform.

## Software Required:

Anaconda - Python 3.7

## Algorithm:

### Step 1 :

Read image and convert it to grayscale image.

### Step 2 :

Find the edges in the image using canny detector and display.

### Step 3:

Detect points that form a line using HoughLinesP.

### Step 4:

Draw lines on the image.

### Step 5:

Display the result.


## Program:

## DEVELOPED BY : ABRIN NISHA A
## REG NO : 212222230005

### Read image and convert it to grayscale image :

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("road.jpg",0)
img_c=cv2.imread("road.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```

### Find the edges in the image using canny detector and display :

```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```

### Detect points that form a line using HoughLinesP :
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image :
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```

### Display the result :
```python
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output :


### Input image and grayscale image :

![Screenshot 2023-04-20 133140](https://user-images.githubusercontent.com/118889454/233300359-4943648f-2f30-4016-aca2-ec90457dfa0e.png)


### Canny Edge detector output :





### Display the result of Hough transform :





## Result:

Thus the program is written with python and OpenCV to detect lines using Hough transform. 
