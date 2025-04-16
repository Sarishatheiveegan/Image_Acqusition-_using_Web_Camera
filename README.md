## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
Write the image using imwrite()

### Step 4:
Display the frame using the imshow().

### Step 5:
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
``` Python
### Developed By:MARINO SARISHA T
### Register No:212223240084

## i) Write the frame as JPG file
import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()

## ii) Display the video
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![Screenshot 2025-04-16 104004](https://github.com/user-attachments/assets/620d2c1c-42d4-43cb-a723-4ca60cf104a8)

### ii) Display the video

![Screenshot 2025-04-16 104126](https://github.com/user-attachments/assets/d1131da9-3615-4ba9-a0c7-cd337271b413)

### iii) Display the video by resizing the window
![Screenshot 2025-04-16 104231](https://github.com/user-attachments/assets/661f5617-bc5b-4ec2-898e-55ee780a86b5)

### iv) Rotate and display the video


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
