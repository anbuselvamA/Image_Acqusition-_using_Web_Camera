# EX-02
# Image_Acqusition-_using_Web_Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
###Step 1:
Use cv2.VideoCapture(0) to access web camera

###Step 2:
Use cv2.imread to read the video or image

###Step 3:
Use cv2.imwrite to save the image

###Step 4:
Use cv2.imshow to show the video

###Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: A.Anbuselvam
### Register No: 212222240009
```
##  i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("image.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('video capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
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
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![dip2 1](https://github.com/PuliNagaNeeraj/Image_Acqusition-_using_Web_Camera/assets/138849173/8bdf8ebb-db8b-4abd-85a6-b38f78c557fe)

</br>
</br>


### ii) Display the video
![dip-2 2](https://github.com/PuliNagaNeeraj/Image_Acqusition-_using_Web_Camera/assets/138849173/219553c1-c87a-431a-a636-28add8d8ef79)

</br>
</br>

### iii) Display the video by resizing the window

![image](https://github.com/PuliNagaNeeraj/Image_Acqusition-_using_Web_Camera/assets/138849173/0f809a93-7134-40f4-b190-b38138d95228)


</br>
</br>

### iv) Rotate and display the video

![dip-2 4](https://github.com/PuliNagaNeeraj/Image_Acqusition-_using_Web_Camera/assets/138849173/9eeb243f-e525-4378-a315-5fe964514604)

</br>
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
