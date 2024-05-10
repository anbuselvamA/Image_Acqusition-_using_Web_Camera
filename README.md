# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:

### Developed By: SAFEEQ FAZIL A
### Register No: 212222240086

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("safeeq.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

```



## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('image',frame)
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
    cv2.imshow('212222240086_safeeq',image)
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
    cv2.imshow('212222240086_safeeq',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```

## Output

### i) Write the frame as JPG image
![Screenshot 2024-02-29 192944](https://github.com/Safeeq-Fazil/Image_Acqusition-_using_Web_Camera/assets/118680361/c8b0286b-c534-4257-969a-5eecda36c129)



### ii) Display the video
![Screenshot 2024-02-29 193043](https://github.com/Safeeq-Fazil/Image_Acqusition-_using_Web_Camera/assets/118680361/d5f3c4c5-00e0-4308-afe1-7757d822bacc)


### iii) Display the video by resizing the window
![Screenshot 2024-02-29 193111](https://github.com/Safeeq-Fazil/Image_Acqusition-_using_Web_Camera/assets/118680361/5342e510-6666-4779-8086-885e74cc124e)



### iv) Rotate and display the video
![image](https://github.com/Safeeq-Fazil/Image_Acqusition-_using_Web_Camera/assets/118680361/dd657881-1c67-4d17-8b5a-8e32b2094cce)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
