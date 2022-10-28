**Answers To Experiment Structure Exercises:**

#-import numpy and/or numpy functions 

    import numpy as np 
    from numpy import (sin, cos, tan, log, log10, pi, average,
                        sqrt, std, deg2rad, rad2deg, linspace, asarray)
    from numpy.random import random, randint, normal, shuffle, choice as randchoice

#-number of trials and blocks

    trial=range(1,11)
    block=range(1,11)

    for trial in trial:
        print("Block 1, Trial number", trial)
    for block in block:
        print("Block 2, Trial number", block)
       
#-stimulus names (and stimulus extensions, if images)

    stimulus= ['object1', 'object2','object3', 'object4', 'object5', 'object6','object7','object8','object9','object10']

    if stimulus ==['object1', 'object2','object3', 'object4', 'object5', 'object6','object7','object8','object10']:
        image = stimulus + '.png'

#-stimulus properties like size, orientation, location, duration

    image1 = visual.ImageStim(
        win=win,
        name='image1', units='pix', 
        image=None, mask=None, anchor='center',
        ori=0.0, pos=(0, 0), size=(200, 200),
        color=[1,1,1], colorSpace='rgb', opacity=None,
        flipHoriz=False, flipVert=False,
        texRes=128.0, interpolate=True, depth=0.0)

#-start message text

    text_3 = visual.TextStim(win=win, name='text_3',
        text='start message',
        font='Open Sans',
        pos=(0, 0), height=0.05, wrapWidth=None, ori=0.0, 
        color='white', colorSpace='rgb', opacity=None, 
        languageStyle='LTR',
        depth=0.0);
        
#-create counterbalanced list of all conditions


**Answers To Import Exercises:**

#-import numpy and/or numpy functions 

    import numpy, random, time

#-import psychopy functions 

    from psychopy import core, gui, visual, event

#-import file save functions  

    import json

#-(import other functions as necessary: os...)

    import os
    
**Answers To Directory Exercises:**

1. 
