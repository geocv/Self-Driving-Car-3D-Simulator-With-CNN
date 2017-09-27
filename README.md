# Self-Driving-Car-3D-Simulator-With-CNN
<p>
  <img align="left" width="425" height="400" src="https://github.com/sagar448/Self-Driving-Car-3D-Simulator-With-CNN/blob/master/src/3D%20Car%20Simulator.png">
  <img align="right" width="420" height="400" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Python.svg/2000px-Python.svg.png">
</p>
<p>
  <img align="center" width="600" height="7" src="http://getthedrift.com/wp-content/uploads/2015/06/White-Space.png">
</p>

## Introduction

Some point in our life as programmers we all wonder how a self driving car is actually made. I went through the same phase and so here it is, a very simple DIGITAL self driving car controlled using Python with a Reinforcement Q-learning algorithm as well as a Convolutional Neural Network.

You can essentially apply this to any game, the algorithm can be adapted and the reward rules can be changed to allow for different outcomes. I will go through the code step by step explaining what each line does and once you've mastered it you can go ahead fork the code and do as you wish.

```
Note: You need to have sufficient knowledge about Reinforcment learning before progressing, this tutorial 
only explains the code it does not go into the theoretical details
The links below help explain the theoretical details:

```

We will be using Keras to make the magic happen with Tensorflow backend. Assuming you are familiar with Keras and Tensorflow and have them installed we can start!

```
Note: Check my other gits for brief explanation on Keras and other simple algorithms such as the CNN 
and RNN if you are unfamiliar with Keras/Tensorflow!
```

## My Setup

In order to detect lanes, we need to send frames of ourr game to the algorithm for processing. I used a library called mss (MultipleScreenShot), it allows the users to take quick screenshots with almost minimal effect in FPS.
Unfortunately, it takes the screen shot of the entire screen if coordinates aren't specified therefore in order to just get the frames of the game, the game needs to be positioned and be in focus. 

The picture below depicts my environment.

<p>
  <img align="Center" width="425" height="400" src="https://github.com/sagar448/Self-Driving-Car-3D-Simulator-With-CNN/blob/master/src/Environment.png">
</p>
<p>
  <img align="centre" width="600" height="7" src="http://getthedrift.com/wp-content/uploads/2015/06/White-Space.png">
</p>
## Implementation
### Imports
```python
1     import cv2
2     import mss
3     import numpy as np
4     from keras.models import Sequential
5     from keras.layers import Dense, Flatten
6     from keras.optimizers import SGD
7     from keras.layers.convolutional import Conv2D
8     import pyautogui as p
9     import random
10    import time
```
