**Answer to Dialogue Box Exercise**

1. 

    exp_info = {'Session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':('male','female','other','prefer not to say')}

2. 

    from psychopy import gui

    exp_info = {'session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':()}

    print(exp_info)
    my_dlg = gui.DlgFromDict(dictionary=exp_info)

1. 

    from psychopy import gui

    exp_info = {'session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':()}
    dictDlg = gui.DlgFromDict(dictionary=exp_info,
            title='Subject Info')
                  
2. 

    from psychopy import gui

    exp_info = {'session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':()}
    dictDlg = gui.DlgFromDict(dictionary=exp_info,
            title='Subject Info',fixed='session')
        
3. 

    from psychopy import gui

    exp_info = {'session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':()}
    dictDlg = gui.DlgFromDict(dictionary=exp_info,
            title='Subject Info',fixed='session',
            order=['session', 'subject_nr', 'age', 'gender', 'handedness'])
            
*4. 

        from psychopy import gui

        exp_info = {'session':1,'subject_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                    'gender':()}
        dictDlg = gui.DlgFromDict(dictionary=exp_info,
                show=False,  #Not sure what to do after putting False...!
                title='Subject Info',fixed='session',
                order=['session', 'subject_nr', 'age', 'gender', 'handedness'])

5.

    from datetime import datetime
    from psychopy import gui

    exp_info = {'participant_nr':0, 'age':0, 'handedness':('right','left','ambi'), 
                'gender':('male','female','other','prefer not to say')}
    dictDlg = gui.DlgFromDict(dictionary=exp_info,
            title='Subject Info',
            order=['participant_nr', 'age', 'gender', 'handedness'],)

    date=datetime.now()
    print(date)

    exp_info['date'] = str(date.day) + str(date.month) + str(date.year)
    print(exp_info['date'])

    filename = str(exp_info['participant_nr']) + '_' + exp_info['date'] + '.csv'
    print(filename)     
    
**Answers to Monitor and Windows Exercise**

1. 

Some units will require monitor information whereas some will not. It defines the default units of stimuli drawn in the window. The different units are beneficial in that you can specify the unit of your choice depending on your circumstance. For conducting demos, the two normalised units (‘norm’ and ‘height’) are handy because the stimulus scales naturally with the window size. For running an experiment it’s best to use ‘cm’ or ‘deg’ so that the stimulus is a fixed size irrespective of the monitor/window. But for all units, the centre of the screen is represented by coordinates (0,0), negative values mean down/left, positive values mean up/right. Therefore, changing units can change the way stimuli are fitted into the window. 

2. 

From Builder you can use the color picker to choose the color you want and find out the value that color would correspond to in a variety of spaces. Psychopy uses three color spaces; RGB, DKL and LMS. Colors can also be specified by a name or by a hexadecimal string.
Colorspace allows you to insert color by name but do not include any spaces. These color names are then converted into RGB space by PsychoPy.

3. 
     
         
 
        from psychopy import visual, monitors
        mon = monitors.Monitor('myMonitor', width=30, distance=57)
        mon.setSizePix([1024,768])
        win = visual.Window(monitor=mon)
        win = visual.Window(monitor=mon, size=(800,800), color=[1.0000, 0.8824, 0.9216],units='None',fullscr=True)
    
**Answers to Stimulus Exercises**

1. 

        from psychopy import visual, monitors, event

        mon = monitors.Monitor('myMonitor', width=30, distance=57)
        mon.setSizePix([1024,768])
        win = visual.Window(monitor=mon) 

        import os
        os.chdir('/Applications')
        main_dir = os.getcwd() 
        image_dir = os.path.join(main_dir,'image')

        import numpy as np 
        stims = ['face01.jpg','face02.jpg','face03.jpg'] 
        nTrials=3 
        my_image = visual.ImageStim(win,units="pix",size=(400,400))

        for trial in range(nTrials): 
            my_image.image = os.path.join(image_dir,stims[trial])

            my_image.draw() 
            win.flip() 
            event.waitKeys() 

        win.close()

2. 

        from psychopy import visual, monitors, event

        mon = monitors.Monitor('myMonitor', width=30, distance=57)
        mon.setSizePix([1200,1200])
        win = visual.Window(monitor=mon) 

        import os
        os.chdir('/Applications')
        main_dir = os.getcwd() 
        image_dir = os.path.join(main_dir,'image')

        face01 = visual.ImageStim(win, units='pix',image='/Applications/image/face01.jpg',pos=(200,100), size=(400,400))
        face02 = visual.ImageStim(win,units='pix',image='/Applications/image/face02.jpg',pos=(-200,100), size=(400,400))
        face03 = visual.ImageStim(win, units='pix',image='/Applications/image/face03.jpg',pos=(-200,-100), size=(400,400))
        face04 = visual.ImageStim(win, units='pix',image='/Applications/image/face04.jpg',pos=(200,-100), size=(400,400))


        face01.draw()
        win.flip() 
        event.waitKeys() 

        face02.draw()
        win.flip() 
        event.waitKeys() 

        face03.draw()
        win.flip() 
        event.waitKeys() 

        face04.draw()
        win.flip() 
        event.waitKeys() 

        win.close()
               
3.

            fix = visual.TextStim(win,text='+')
            fix_text.draw()
4.

        #=====================
        #CREATION OF WINDOW AND STIMULI
        #=====================
        #-define experiment start text unsing psychopy functions
        start_msg = "Welcome to my experiment!"
        #-define block (start)/end text using psychopy functions
        block_msg = "Press any key to continue to the next block."
        end_trial_msg = "End of trial"
        #-define stimuli using psychopy functions (images, fixation cross)
        stims = ['face01.jpg','face02.jpg','face03.jpg']
        fix = visual.TextStim(win,text='+')
        #=====================
        #START EXPERIMENT
        #=====================
        #-present start message text
        start_msg = "Welcome to my experiment!"
        my_text = visual.TextStim(win, text=start_msg)
        #-allow participant to begin experiment with button press
        my_text = visual.TextStim(win, text=block_msg)
        event.waitKeys()
        #=====================
        #BLOCK SEQUENCE
        #=====================
        #-for loop for nBlocks
        for block in range(nBlocks):
            #-present block start message
            visual.TextStim(win, text=block_msg)
            #-randomize order of trials here
            import numpy as np
            np.random.shuffle(trials)
            #=====================
            #TRIAL SEQUENCE
            #=====================    
            #-for loop for nTrials
            for trial in range(nTrials):
                #-set stimuli and stimulus properties for the current trial
                my_image = visual.ImageStim(win,units="pix",size=(400,400))

                #=====================
                #START TRIAL
                #=====================  
                #-draw fixation
                fix_text.draw()
                #-flip window
                win.flip()
                #-wait time (stimulus duration)
                core.wait(3)

                #-draw image
                pic_loc = os.path.join(image_dir,'face01.jpg')
                my_image = visual.ImageStim(win, image=pic_loc)
                my_image.draw()
                #-flip window
                win.flip()
                #-wait time (stimulus duration)
                core.wait(3)

                #-draw end trial text
                end_trial_text.draw()
                #-flip window
                win.flip()
                #-wait time (stimulus duration)
                core.wait(3)
        #======================
        # END OF EXPERIMENT
        #======================        
        #-close window
        win.close()
