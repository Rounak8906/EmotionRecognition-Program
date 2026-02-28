# EmotionRecognition-Program
## Facial Emotion Recognition:
This is a python project using torch and opencv Libraries.
In this project through pyhton code we can detect facial emotions of human detecting throgh the device camera. There are several steps to be followed to run the code. Steps are as followed:
### Step 1:
Install Python idle between versions 3.9.6 and 3.12.0
### Step 2:
After installation search for the idle in windows then right click to go into file location via clicking ```Open file location```; then after right clickon ```python idle version 3.__``` to open file location via clicking ```Open file location```.
### Step 3:
Inside file location go to ```Scripts``` and int he path option above type ```cmd`` to open command prompt. after getting inside command prompt install the following python libraries typing :
1. pip install numpy
2. pip install pandas 
3. pip install opencv-contrib-python
4. pip install torch
5. pip install torchvision
### Step 4:
After installing go back to python idle file location and go to ```Lib``` (just above ```Scripts```) after  going follow this path:
```Lib``` ----> ```site packages``` ----> ```torch``` ----> ```serialization```
### Step 5:
In the ```serialization```,right click and choose the option ```edit with Notepad```,
after opeing the file in Notepad press ```ctrl + f``` and search for ``` def load```.
In ```def load``` change :
```
def load(
    f: FileLike,
    map_location: MAP_LOCATION = 'None',
    pickle_module: Any = None,
    *,
    weights_only: Optional[bool] = None,
    mmap: Optional[bool] = None,
    **pickle_load_args: Any,
) 
```
to 
```
def load(
    f: FileLike,
    map_location: MAP_LOCATION = 'cpu',
    pickle_module: Any = None,
    *,
    weights_only: Optional[bool] = None,
    mmap: Optional[bool] = None,
    **pickle_load_args: Any,
) 
```
### Step 6:
Now open pyhton idle file to write the python progam for the project : 
```
from facial_emotion_recognition import EmotionRecognition
import cv2

er=EmotionRecognition(device='cpu')
cam=cv2.VideoCapture(0)

while True:
    sucess,frame = cam.read()
    frame=er.recognise_emotion(frame,return_type='BGR')
    cv2.imshow("Frame",frame)
    key=cv2.waitKey(1)
    if key==27:
        break
cam.release()
cv2.destroyAllWindows()
```
After writing this code run the program
### Step 7:
Run the program and a frame will open in which :
Your human face emotion recognition with emotions like Sad,happy,Angry,Confused or evenNeutral will be detected with 95% accuracy.
## Output:
The human face recognition project works suuccesfully with 95% accuracy.