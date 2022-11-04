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

    textWelcomeMessage = visual.TextStim(win=win, name='textWelcomeMessage',
        text='Welcome to the experiment!',
        font='Open Sans',
        pos=(0, 0), height=0.05, wrapWidth=None, ori=0.0, 
        color='white', colorSpace='rgb', opacity=None, 
        languageStyle='LTR',
        depth=0.0);
        
#-create counterbalanced list of all conditions

    stimulus=['object1', 'object2','object3', 'object4', 'object5', 'object6','object7','object8','object9','object10']
    imgs=['im1.png', 'im2.png', 'im3.png', 'im4.png', 'im5.png','im6.png','im7.png','im8.png','im9.png','im10.png']

    stimulusimgs = list(zip(stimulus,imgs))
    print(stimulusimgs)
    
#-create an empty list for correct responses

    correctresponses=[]
    correctresponses.append()
    print(correctresponses)

#-create an empty list for participant responses

    responses=[]
    responses.append()
    print(responses)

#-create an empty list for response accuracy collection

    responsesaccuracy=[]
    responsesaccuracy.append()
    print(responsesaccuracy)

#-create an empty list for response time collection

    responsetime=[]
    responsetime.append()
    print(responsetime)

#-create an empty list for recording the order of stimulus identities

    responseorderidentities=[]
    responseorderidentities.append()
    print(responseorderidentities)

#-create an empty list for recording the order of stimulus properties

    responsesproperties=[]
    responsesproperties.append()
    print(responsesproperties)

#-for loop for nBlocks
    
       block = data.TrialHandler(nReps=2.0, method='random', 
        extraInfo=expInfo, originPath=-1,
        trialList=data.importConditions('image_faces.xlsx'),
        seed=None, name='block')
    thisExp.addLoop(block)  
    thisBlock = block.trialList[0] 

    if thisBlock != None:
        for paramName in thisBlock:
            exec('{} = thisBlock[paramName]'.format(paramName))

    for thisBlock in block:
        currentLoop = block

        if thisBlock != None:
            for paramName in thisBlock:
                exec('{} = thisBlock[paramName]'.format(paramName))


#-randomize order of trials here

    np.random.shuffle(trials)
   
#-for loop for nTrials

    face_imagesloop = data.TrialHandler(nReps=1.0, method='random', 
            extraInfo=expInfo, originPath=-1,
            trialList=data.importConditions('image_faces.xlsx'),
            seed=None, name='face_imagesloop')
        thisExp.addLoop(face_imagesloop)  # add the loop to the experiment
        thisFace_imagesloop = face_imagesloop.trialList[0]  
    
        if thisFace_imagesloop != None:
            for paramName in thisFace_imagesloop:
                exec('{} = thisFace_imagesloop[paramName]'.format(paramName))

        for thisFace_imagesloop in face_imagesloop:
            currentLoop = face_imagesloop
           
            if thisFace_imagesloop != None:
                for paramName in thisFace_imagesloop:
                    exec('{} = thisFace_imagesloop[paramName]'.format(paramName))

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
