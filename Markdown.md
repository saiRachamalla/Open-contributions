
# open-contributions
**HERE,I want to share some basic things i have learned from DEVINCEPT modules**
  
## markdown
**It may creates documents with an explicit structure**

_why markdown?_ 
* Easy The syntax is very simple.

* Fast: It speeds up the workflows.

* Clean: No missing closing tags, no improperly nested tags, no blocks left without containers.

* Portable: Cross-platform by nature.

* Flexible: Output documents to a wide array of formats like, convert to HTML , rich text for sending emails or any number of other proprietary formats.


_so,Here u can get some basic idea about mardown_
 _Go through the link to learn more_
[introduction](https://github.com/DevIncept/Prerequisite-Module/blob/421d7b19bea94b7b9f2a52106be4f48809e25d00/Markdown.md).
***
# openCV
 openCv(open source Computer Vision Library) is a library of programming functions mainly aimed at real time computer vision.
### opencv's application areas include:
* 2D and 3D feature toolkits.
* Egomotion estimation.
* Facial recognition system.
* Gesture recognition.
* Object detection.
## numpy
[numpy](https://github.com/saiRachamalla/OpenCV/blob/77b327ac9cdfe37cc67debb68dfa4bc272381794/Part1.md)

## computer vision
[computer vision](https://github.com/DevIncept/OpenCV/blob/77b327ac9cdfe37cc67debb68dfa4bc272381794/part5.md)

[Basic operations with opencv](https://github.com/DevIncept/OpenCV/blob/77b327ac9cdfe37cc67debb68dfa4bc272381794/part7.md)
## segmentation
 **Image segmentation** is typically used to locate objects and boundaries (lines, curves, etc.) in images. More precisely, image segmentation is the process of assigning a label to every pixel in an image such that pixels with the same label share certain characteristics.

practical applications of segmentation:

* object detection 

* medical imaging 

* Recognition tasks 
* Traffic control systems 
# contours
Contours are mainly used in Object Detection. Working with contours is very handy and have application in determining the size and shape of an object. Briefly stating, Contour finds its applications in anything that involves shape analysis, object detection and recognition.

# Object detection
OpenCV is the huge open-source library for computer vision, machine learning, and image processing and now it plays a major role in real-time operation which is very important in today’s systems. By using it, one can process images and videos to identify objects, faces, or even the handwriting of a human. This article focuses on detecting objects.
### Object Detection
Object Detection is a computer technology related to computer vision, image processing, and deep learning that deals with detecting instances of objects in images and videos. We will do object detection in this article using something known as haar cascades.
### Haar Cascades
Haar Cascade classifiers are an effective way for object detection. Haar Cascade is a machine learning-based approach where a lot of positive and negative images are used to train the classifier.

**Positive images** – These images contain the images which we want our classifier to identify.

**Negative Images**– Images of everything else, which do not contain the object we want to detect.

_EXAMPPE:_

![input image](https://media.geeksforgeeks.org/wp-content/uploads/20200122210935/image28.jpg)
`
import cv2
from matplotlib import pyplot as plt
  
##### Opening image
img = cv2.imread("image.jpg")
  
###### OpenCV opens images as BRG but we want it as RGB and we also need a grayscale version
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  
###### Creates the environment of the picture and shows it
plt.subplot(1, 1, 1)
plt.imshow(img_rgb)
plt.show()
`
##### Recognition

We will use the detectMultiScale() function of OpenCV to recognize big signs as well as small ones:
`
###### Use minSize because for not bothering with extra-small dots that would look like STOP signs

found = stop_data.detectMultiScale(img_gray, 
                                   minSize =(20, 20))
  
###### Don't do anything if there's no sign
amount_found = len(found)
  
  
if amount_found != 0:
      
    ##### There may be more than one sign in the image
    for (x, y, width, height) in found:
          
        ##### We draw a green rectangle around every recognized sign
        cv2.rectangle(img_rgb, (x, y), 
                      (x + height, y + width), 
                      (0, 255, 0), 5)
`
###### output:
![object detection](https://media.geeksforgeeks.org/wp-content/uploads/20200122210826/stop_recognition_output.png)
