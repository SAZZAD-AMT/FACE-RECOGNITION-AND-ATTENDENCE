<h1>FACR-RECOGNITION-AND-ATTENDENCE</h1>

![FACE DETECTION](https://github.com/SAZZAD-AMT/FACE-RECOGNITION-AND-ATTENDENCE/blob/main/Imagesbasic/Elon1.jpg)


- ALL OF YOU PLEASE INSTALL PIP PERFECTLY.
---
<li>What is used for face detection?</li>
<p>Face detection is AI-based computer technology that is used to extract and identify human faces from digital images. When integrated with biometric security systems (particularly, facial recognition ones), this kind of technology is what makes it possible to monitor and track people in real-time.</p>
<li>How does face detection work?</li>
<p>A facial recognition system uses biometrics to map facial features from a photograph or video. It compares the information with a database of known faces to find a match. Facial recognition can help verify a person's identity, but it also raises privacy issues.</p>

---

# FACE RECOGNITION

```
imgElon = face_recognition.load_image_file('Imagesbasic/Elon Musk.jpg')
imgElon = cv2.cvtColor(imgElon,cv2.COLOR_BGR2RGB)
imgTest = face_recognition.load_image_file('Imagesbasic/Elon1.jpg')
imgTest = cv2.cvtColor(imgTest,cv2.COLOR_BGR2RGB)
```
```
results = face_recognition.compare_faces([encodeElon],encodeTest)
faceDis = face_recognition.face_distance([encodeElon],encodeTest)
print(results,faceDis)
cv2.putText(imgTest,f'{results} {round(faceDis[0],2)}',(50,50),cv2.FONT_HERSHEY_COMPLEX,1,(0,0,255),2)
```
---
# FACE RECOGNITION FOR ATTENDENCE
```
import cv2
import numpy as np
import face_recognition
import os
from datetime import datetime
# from PIL import ImageGrab
```
```
def markAttendance(name):
    with open('Code\Att.csv','r+') as f:
        myDataList = f.readlines()
        nameList = []
        for line in myDataList:
            entry = line.split(',')
            nameList.append(entry[0])
        if name not in nameList:
            now = datetime.now()
            dtString = now.strftime('%H:%M:%S')
            f.writelines(f'\n{name},{dtString}')
```
---
# PLEASE CHECK CSV FILE. There you can see attendance.