# Vityarthi-Project
## Face Recognition and Detection System

A simple face recognition system built using **Google Teachable Machine** and OpenCV.  
The model is trained with images of only two people to keep it fast, lightweight, and accurate.

### Demo
![Sample output](https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/Face_recog_sample.jpeg?raw=true)

### Features
- Real-time face detection using Haar Cascades
- Recognition using a Keras model exported from Teachable Machine
- Data collection script (`datacollect.py`) that captures 500 images per person
- Live prediction with name labels in `test.py`

### Code Snippets

**1. Data collection setup**
```python
import cv2
import os
video = cv2.VideoCapture(0)
facedetect = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
```
</br> 

<p> This Code snippet enables the camera to capture pictorial data and store it in a folder.</p>

</br> 


2. The image folder
``` python
path='images/'+nameID

isExist = os.path.exists(path)

if isExist:
	print("Name Already Taken")
	nameID=str(input("Enter Your Name Again: "))
else:
	os.makedirs(path)
```
</br>
<p> This code introduces a image folder and checks for the path if it is already made then the images are stored in that folder else it will create that folder to store the data. </p>


</br>

3. The Prediction model

```python
while True:
	sucess, imgOrignal=cap.read()
	faces = facedetect.detectMultiScale(imgOrignal,1.3,5)
	for x,y,w,h in faces:
		crop_img=imgOrignal[y:y+h,x:x+h]

		crop_img = imgOrignal[y:y+h, x:x+w]          
		img = cv2.resize(crop_img, (224, 224))
		img = img.astype("float32") / 255.0          
		img = np.expand_dims(img, axis=0)            

		prediction = model.predict(img, verbose=0)   
		prediction = tf.nn.softmax(prediction)       
		classIndex = np.argmax(prediction, axis=1)[0]
		probabilityValue = np.max(prediction)     

```

<p>This code is the prediction model of the face detection system it runs until the camera reads and captures human faces then uses its prediction model by alinging to the data provided to it via the google teachable machine . </p>

</br>

```python
prediction = tf.nn.softmax(prediction)
```
<p>The softmax function converts a vector of raw scores (also called logits) into a probability distribution</p>

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
5. Make sure to provide proper local path to the `haarcascade_frontalface_default.xml`.

</br>


 ### Screenshots
 </br>

<div align="center">

<img src="https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/check_adar_recog.png?raw=true" width="48%"  />
<img src="https://github.com/adarsh25bai10019-source/Vityarthi-Project/blob/main/check_recog.jpeg?raw=true" width="48%" />

</div
   

