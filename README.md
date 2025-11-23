# Vityarthi-Project
## FACE RECOGNITION AND DETECTION SYSTEM
<p>A face recognition and detection system is basically a technology which detects the face a of a person based on provided training datasets. It is a rule based model which predicts output based on historical data provided to the machine . In my project I have used google teachable machine to train my machine (https://teachablemachine.withgoogle.com/). I have used the image model to feed the image datasets of two people. It is restricted to only two people to avoid increasing time and space complexity and making my model more reliable and quick . I have used many libraries which i will be discussing further in the modules section. The code is basically divided into two code frameworks one is to collect data which collects 500 images of the person. This is repeated for the other person also.Then the other code framework is the test.py which is the includes the main code of the project .</p>

</br>

![A sample image of the project](https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/Face_recog_sample.jpeg?raw=true)

</br>

 ### Features 📚

```python

import cv2
import os

video=cv2.VideoCapture(0)

facedetect=cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
```
</br> 

<p> This Code snippet enables the camera to capture pictorial data and store it in a folder.</p>

</br>

```python

facedetect = cv2.CascadeClassifier('/Users/adarshtiwari/Desktop/face_recognition_system-main/Face Recognition System/haarcascade_frontalface_default.xml')
cap=cv2.VideoCapture(1)
cap.set(3, 640)
cap.set(4, 480)
font=cv2.FONT_HERSHEY_COMPLEX
model = load_model('/Users/adarshtiwari/Desktop/face_recognition_system-main/Face Recognition System/keras_model.h5')
def get_className(classNo):
	if classNo==0:
		return "Adarsh"
	elif classNo==1:
		return "Nirmala Sitaraman"
```
<p>This is a code snippet from the test.py and it opens the camera indexed 1 which is the secondary camera , cv2.cVideoCapture(0) opens the primary camera. </p>
<p>Then we load the keras model which is downloaded from the google teachebale machine and def the categories for which the machine has to dispaly the tag. </p>
<p>If the model matches the data with the historical data from either of the category it will return 0 and 1 . </p>

</br>

 ### The libraries involved in this project : 

```markdown
tensorflow
numpy
cv2
os
```
<br>

You can download these libraries using the pip command, a example is shown below.

```markdown
pip install tensorflow
```

</br>

 ### Steps to install and run the project :  
</br>
1. Download the zip file from github repository.
</br>
2. Unzip the file in your local environment.
</br>
3. Open the python files in a code editor.
</br>
4. Collect visual data by inputting your name in the datacollect.py module.
</br>
5. Feed the data in google teachebale machine (https://teachablemachine.withgoogle.com/).
</br>
6. Download the keras model optimised for your visual data.
</br>
7. Run the test.py module and change the labels for the image accoridng to your prefernce.

</br>
</br>


 ### Important instructions for testing and using the code. 

1. Check whether the indentation is correct.
2. Make sure to place the supporting modules are in the correct folder.
3. Make sure to provide the correct path to the modules.
4. In the github zip the a "image" folder must be created by the user else the machine will throw an error.

<div align="center">

<img src="https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/check_adar_recog.png?raw=true" width="48%"  />
<img src="https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/Face_recog_sample.jpeg?raw=true" width="48%" />

</div
   

