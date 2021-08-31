# Magic_Project
---

Hello Friends,
Today we are going to do magic not by using magic trick but by using Python.Isn't it sound intresting?Offcourse yes!!!!!!!!!
So lets start building our own invisible cloak using computer vision in python.
For working on this project we need to know 3 things :
1)Python - 3.x (we used Python 3.9.6 in this project)
2)Numpy - 1.19.2
3)OpenCV - 4.5
We are using VSCode editor for this project.
Steps:
Create new Project in VSCode .
Create new file "magic.py"
Open Terminal & Type:

pip install opencv-python
pip install numpy
4.And now start writting code for project& for code go with following flow.

![project_flow](https://user-images.githubusercontent.com/67435373/131524760-7632d457-3b08-4c35-85e1-47c52ac4637a.png)




Importing needed libraries

import numpy as np
import cv2
import time


2. Recording and caching the background for each frame.
cap=cv2.VideoCapture(0)
#for the system to sleep for 3 second before the webcam starts
time.sleep(3)

3.Capturing background & Video.
for i in range(30):
    retval,back=cap.read()
back=np.flip(back,axis=1)
cap=cv2.VideoCapture(0)

4.Read every frame & convert BGR->HSV
#Read every Frame from the webcam, until the camera is open
while (cap.isOpened()):
   ret,img=cap.read()
   if ret:
      img=np.flip(img,axis=1)
      #convert the color space from BGR to HSV
      hsv=cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
      
5.Setting values for cloak & mask.
here I have selected color as red you can choose of your own and set lower and upper values accordingly.
      #Generat masks to detect red color
      lower_red = np.array([0,120,70])
      upper_red = np.array([10,255,255])
      mask1 = cv2.inRange(hsv,lower_red,upper_red)

      lower_red = np.array([170,120,70])
      upper_red = np.array([180,255,255])
      mask2 = cv2.inRange(hsv,lower_red,upper_red)
      mask1+=mask2
      
6.Using Morphological Transformation to remove noise from cloth and unnecessary things.
      mask = cv2.morphologyEx(mask1, cv2.MORPH_OPEN, np.ones((5,5),np.uint8))
      img[np.where(mask==255)]=back[np.where(mask==255)]
      
7.Combining mask & showing in one frame.
      cv2.imshow("Surprise",img)
   key = cv2.waitKey(1)
   if key==ord("q"):
      break
cap.release()
cv2.destroyAllWindows()

