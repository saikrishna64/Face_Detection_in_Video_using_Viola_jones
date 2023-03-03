<!DOCTYPE html>
<html>
<head>
	<title>Face Detection using Viola Jones</title>
</head>
<body>
	<h1>Face Detection using Viola Jones Algorithm</h1>
	<p>In this project, we will be using the Viola Jones algorithm to detect faces in a video stream. The Viola Jones algorithm is a popular method for detecting objects in images and videos. It uses Haar-like features to detect objects, and a cascade classifier to quickly classify regions of an image or video as object or non-object.</p>
<h2>Requirements</h2>
<ul>
	<li>OpenCV Library</li>
	<li>Python 3.x</li>
	<li>Numpy Library</li>
	<li>Video file</li>
	<image src='https://3.bp.blogspot.com/-yvrV6MUueGg/ToICp0YIDPI/AAAAAAAAADg/SYKg4dWpyC43AAfrDwBTR0VYmYT0QshEgCPcBGAYYCw/s1600/OpenCV_Logo.png' height=100, width=125>
	<image src='https://www.python.org/static/opengraph-icon-200x200.png' height=100, width=100>
	<image src='https://devocean.sk.com/CKFinderJava/userfiles/images/numpy(1).png' height=100, width=100>
</ul>

<h2>Installation</h2>
<p>To install the required libraries, use the following commands:</p>
<pre>
	<code>pip install opencv-python</code>
	<code>pip install numpy</code>
</pre>

<h2>Usage</h2>
<p>First, create a new Python file and import the necessary libraries:</p>
<pre>
	<code>import cv2
import numpy as np</code>
</pre>


<p>Then, load the video file using OpenCV:</p>
<pre>
	<code>cap = cv2.VideoCapture('video.mp4')</code>
</pre>

<p>Next, load the pre-trained Haar cascade classifier for face detection:</p>
<pre>
	<code>face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')</code>
</pre>

<p>Finally, loop through each frame of the video, detect faces using the Viola Jones algorithm, and draw rectangles around the detected faces:</p>
<pre>
	<code>while True:
ret, frame = cap.read()
if ret == False:
    break
    
gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
faces = face_cascade.detectMultiScale(gray, 1.3, 5)

for (x,y,w,h) in faces:
    cv2.rectangle(frame,(x,y),(x+w,y+h),(255,0,0),2)
    
cv2.imshow('Face Detection',frame)
if cv2.waitKey(1) & 0xFF == ord('q'):
    break
cap.release()
cv2.destroyAllWindows()</code>
</pre>


<p>Save the file and run it to start detecting faces in the video stream.</p>

<h2>Conclusion</h2>
<p>The Viola Jones algorithm is an effective method for detecting objects in images and videos. By using Haar-like features and a cascade classifier, we can quickly and accurately detect faces in a video stream using OpenCV and Python.</p>
<image src='https://cdn.technologyreview.com/i/images/Face%20detection.png' height=200, width=375>
</body>
</html>



