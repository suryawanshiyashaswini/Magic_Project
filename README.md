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

<img width="265" alt="1" src="https://user-images.githubusercontent.com/67435373/131543101-afe7997f-421e-40ee-96a2-3cc5302ac7b4.png">
4.And now start writting code for project& for code go with following flow.

![project_flow](https://user-images.githubusercontent.com/67435373/131524760-7632d457-3b08-4c35-85e1-47c52ac4637a.png)








1.Importing needed libraries

<img width="258" alt="2" src="https://user-images.githubusercontent.com/67435373/131543147-8ad9f80e-aa52-40a2-96b6-4cede8954d2b.png">

2. Recording and caching the background for each frame.

<img width="498" alt="3" src="https://user-images.githubusercontent.com/67435373/131543834-7ee6733d-f2d3-4a23-b9e6-08c66f94323e.png">
3.Capturing background & Video.

<img width="302" alt="4" src="https://user-images.githubusercontent.com/67435373/131543889-33e85444-9acc-4c90-9e12-b22d20542ca5.png">

4.Read every frame & convert BGR->HSV

<img width="467" alt="5" src="https://user-images.githubusercontent.com/67435373/131543943-9520f29e-13a4-408d-9535-916823d80320.png">
      
5.Setting values for cloak & mask.
here I have selected color as red you can choose of your own and set lower and upper values accordingly.
      
<img width="440" alt="6" src="https://user-images.githubusercontent.com/67435373/131544000-238b1bc4-90b1-494f-8b95-7ab56f5677b4.png">


      
6.Using Morphological Transformation to remove noise from cloth and unnecessary things.
<img width="442" alt="7" src="https://user-images.githubusercontent.com/67435373/131544037-776f24b1-d8dd-4423-b4f2-7aa3f2f634e3.png">
      
7.Combining mask & showing in one frame.
<img width="307" alt="8" src="https://user-images.githubusercontent.com/67435373/131544081-73d38029-9613-4311-ab3b-5da587e13137.png">
