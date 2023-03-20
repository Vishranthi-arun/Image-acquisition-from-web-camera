# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window <br>
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)
<br>

### Step 2:
Write the captured image using cv2.imwrite("pic.jpg",frame)
<br>

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
<br>

### Step 4:
Display the image until the loop gets over.
<br>

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).
<br>

## Program:
``` Python
### Developed By: Vishranthi A
### Register No: 212221230124

## i) Write the frame as JPG file
import pandas as pd
import cv2
import numpy as np
cam = cv2.VideoCapture(0)
while(True):
    ret,frame = cam.read()
    cv2.imwrite("pic.jpg",frame)
    result = False
cam.release()
cv2.destroyAllWindows()

## ii) Display the video
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
cap = cv2.VideoCapture (0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int (cap.get(4)) 
    image = np.zeros(frame. shape, np. uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image [height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![1](https://user-images.githubusercontent.com/93427278/226400896-41dfd160-8b9b-466b-b2b9-b22271277890.png)

### ii) Display the video
![Screenshot (20)](https://user-images.githubusercontent.com/93427278/226403398-07adb458-76ce-4440-80e3-e11273ce50cc.png)



### iii) Display the video by resizing the window!
![Screenshot (21)](https://user-images.githubusercontent.com/93427278/226403530-8a33ba93-128d-4fe5-bb09-eb3257b26c15.png)





### iv) Rotate and display the video
![Screenshot (22)](https://user-images.githubusercontent.com/93427278/226403475-95c538ad-13cc-4cbb-863f-ddf7b1789b61.png)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
