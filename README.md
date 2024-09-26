## Image_Acqusition_using_Web_Camera
### Date:
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
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:

### Developed By: Ramya R
### Register No: 212223230169

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("Exp2.jpg", frame)
    print("Image saved as Exp2.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()  
```

## iii) Display the video by resizing the window
```
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)  
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![Screenshot 2024-09-26 152239](https://github.com/user-attachments/assets/3908e2ea-9a76-477e-a50e-ae5c390b452e)

### ii) Display the video
![Screenshot 2024-09-26 151441](https://github.com/user-attachments/assets/26002005-ccdc-4b96-9b72-de3932d42127)

### iii) Display the video by resizing the window
![Screenshot 2024-09-26 151610](https://github.com/user-attachments/assets/23a21d6d-e6fc-4951-95df-74a4a84d6157)

### iv) Rotate and display the video
![Screenshot 2024-09-26 151635](https://github.com/user-attachments/assets/ea4c9cee-3c7a-4eb0-a016-4782b15b41d0)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
