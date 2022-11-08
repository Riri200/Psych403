**Answers To Experiment Structure Exercises:**

#-import numpy and/or numpy functions 

    import numpy as np 
    import random
    from psychopy import core, gui, visual, event 
    import os
    
#-number of trials and blocks

    nTrial=10
    nBlock=2
       
#-stimulus names (and stimulus extensions, if images)

    stimulus = ['face01.jpg', 'face02.pjg','face03.jpg', 'face04.jpg', 'face05.jpg', 'face06.jpg','face07.jpg','face08.jpg','face09.jpg','face10.jpg']

#-stimulus properties like size, orientation, location, duration

    image1 = visual.ImageStim(
    win=win,
    name='image1', 
    image='image/face01.jpg', mask=None, anchor='center',
    ori=0.0, pos=(0, 0), size=(0.5, 0.5),
    color=[1,1,1], colorSpace='rgb', opacity=None,
    flipHoriz=False, flipVert=False,
    texRes=128.0, interpolate=True, depth=0.0)

#-start message text

    textWelcomeMessage = visual.TextStim(win=win, name='textWelcomeMessage',
        text='Welcome to the experiment!',
        font='Open Sans',
        pos=(0, 0), height=0.05, wrapWidth=None, ori=0.0, 
        color='white', colorSpace='rgb', opacity=None, 
        languageStyle='LTR',
        depth=0.0);
        
#-create counterbalanced list of all conditions

    stimulus= ['face01.jpg', 'face02.pjg','face03.jpg', 'face04.jpg', 'face05.jpg', 'face06.jpg','face07.jpg','face08.jpg','face09.jpg','face10.jpg']*2
    blocks=['block1']*10 + ['block2']*10

    stimulusBlocks = list(zip(blocks,stimulus))
    print(stimulusBlocks)
    
#-create an empty list for correct responses

    correctresponses=[]

#-create an empty list for participant responses

    responses=[]

#-create an empty list for response accuracy collection

    responsesaccuracy=[]

#-create an empty list for response time collection

    responsetime=[]

#-create an empty list for recording the order of stimulus identities

    responseorderidentities=[]

#-create an empty list for recording the order of stimulus properties

    responsesproperties=[]

#-for loop for nBlocks
    
       for block in range(nBlocks)

#-randomize order of trials here

    np.random.shuffle(nTrials)
   
#-for loop for nTrials

    for trial in range(nTrials)

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

#Question 1:     
  
    import os
    image_dir = os.path.join(main_dir,'images')
    os.listdir(pics)
     
#Question 2:

        for pic in pics:
            if os.path.isdir(directory) == "True"
            print("cat1.jpg was found")
            if os.path.isdir(directory) == "False"
            print("Image does not exist")
            
#Question 3:

    import os

    experiment_dir = os.path.join(main_dir,'experiment')
    data_dir = os.path.join(main_dir,'data')
    image_dir = os.path.join(main_dir,'image)

    path = '/Users/irisshi/Desktop/image'

    path = os.path.isfile(path)
    print(path)
