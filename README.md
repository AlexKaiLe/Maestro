# README

## CSCI 1430 Final Project Report: Remote Control

Alex Le, Ian Acosta, Sophia Tu, Kelly Wang 
Brown University 

### NOTE: For detailed description, please refer to Maestro![image](https://user-images.githubusercontent.com/29731342/134710822-523980f6-6449-4b47-a247-ebfa819f29bb.png)


### Abstract:
We are team TeleVision and we wanted to create a gesture control system where different hand positions can activate different commands on a computer. We created a Convolutional Neural Network to recognize how many fingers—from 0 to 5—a right hand holds up and maps the gestures to commands on a music playlist. This gesture recognition system allows for a different approach to controlling interfaces, increasing accessibility.

### Introduction:
We wanted to create a gesture control system where different hand positions can activate different commands on a computer. We wanted accurate recognition of input images so we tried to create a convolutional neural network for the task. We believe that introducing machine learning into the task would greatly benefit accuracy. Human hands are very complex because they can bend into various shapes and look different from different angles. This makes recognition difficult as different gestures may have similar contours. Nonetheless, we believe that remote control through hand gestures would offer offer an alternate approach to controlling interfaces, increasing accessibility for different groups of people. For those who may have disabilities or difficulties understanding or accessing traditional buttons, having an accurate, and easily learned hand-gesture control would improve accessibility.

### Method:
Rather than using a predefined classification algorithm (such as SIFT), we decided that using a CNN would help us create a more extensible program since we would be able to add more pictures to make the training data more robust. Although this process would take longer because of the extra training step, we figured that this would provide more accurate and consistent results in any type of environment. Our approach was to utilize a CNN to train on a black and white data set of hands to help us classify the amount of fingers a person holds up. As for our CNN, we used a simple three-block architecture that ultimately outputs one of the six hand classifications, which represents each finger count from zero fingers to five fingers.

### Documentation of program commands:
To start the program, set up the cs1430\_env and navigate to the television directory. You also want to make sure you have all the correct libraries installed before running the program. Run the command <python main.py --weights your.weights.e007-acc0.9958.h5>. You can also train your own data using GCP and use the --weights flag to change the weights being used. (ie. <python main.py --weights [your weight file name]>. Once the program loads, you can input what song you would like to play from the prompted list. Once a song is chosen, the camera will load and will wait 30 seconds to calibrate. [NOTE*** for best performance, be in a room with a blank background with a light source point towards you]. There are 4 hands you can use to manipulate the songs by placing your hand in the blue box. The program will read in three frames and choose the mood predicted finger count to execute a command. If the hand is left in the box past the 3rd frame, it will be read in the next cycle. Thus, to prevent the program form continuing to read in your hand gesture, put your hand down once the desire command is read in. The threshold popup demonstrates what image of you hand is being put into the program.


* 0 fingers: Pauses current song
* 1 finger: Shuffles the music to a random song
* 3 fingers: Restarts the current 
* 5 fingers: Resumes/plays current song

There are also two key commands. Because we are using a CNN, clicking on one of these commands may take up to a couple seconds before executing. Once on the the python video feed, you can click:
* c: Changes the song of your desire (input your song choice into the terminal)
     Would you like to change songs? (y/n) 
* q: Quits the program


 
 
