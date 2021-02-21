# Take5
This is a start / stop button for recording music practices. The program starts an audio recording when the user hits the space bar. Hitting the space bar a second time stops and saves the recording. Starting a new recording will delete the previous take. 


## Versions and learning log
### Version 1: Video start, stop, and save.
Version 1 was a copied code from a youtube video on recording video in python. At first the program did not record video but did produce a file. Yinso and I solved this error by properly formatting the VideoCapture method inputs, and releasing the objects in the correct order. In abbreviated pseudo-code, the order appears as this:
```
while("cap" is True):
  ... 
  write the "out" object
  ...

release "cap"
release "out"
close all windows
```
The concept of Last In First Out was important for solving the capturing issue. 

Secondly, searching on Stack Overflow led us to discover that it is necessary for the input resolution and framerate in the VideoWriter method to match the webcam's actual resolution. The line using VideoWriter appears like this after solving the issue:

```
out = cv2.VideoWriter('test15.mp4', fourcc, 15.0, (1280,960))
```

The next version of the program will record audio instead of video and achieve the same function: start recording when the program opens, stop recording when the user hits 'q,' and save the recorded audio to the directory. 
