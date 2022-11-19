**Wait Excercses Answers**

            #=====================
            #START TRIAL
            #===================== 
            #-draw fixation
            fix = visual.TextStim(win,text='+')
            fix_text.draw()
            #-flip window
            win.flip() 
            #-wait time (stimulus duration)
            core.wait()

            #-draw image
            my_image.draw()
            #-flip window
            win.flip() 
            #-wait time (stimulus duration)
            core.wait()

            #-draw end trial text
            end_trial_text.draw()
            #-flip window
            win.flip()
            #-wait time (stimulus duration)
            core.wait()

**Clock Excercises Answers**

1. 

                        from psychopy import visual, monitors, event, core

                        mon = monitors.Monitor('myMonitor', width=30, distance=57)
                        mon.setSizePix([1024,768])
                        win = visual.Window(monitor=mon) 

                        trial_timer = core.Clock()

                        import os
                        os.chdir('/Applications')
                        main_dir = os.getcwd() 
                        image_dir = os.path.join(main_dir,'image')

                        import numpy as np 
                        stims = ['face01.jpg','face02.jpg','face03.jpg'] 
                        nTrials=3 
                        my_image = visual.ImageStim(win,units="pix",size=(400,400))

                        for trial in range(nTrials): 
                            trial_timer.reset()
                            core.wait(2)

                            print('Trial'+str(trial)+' time =', trial_timer.getTime())
                            my_image.image = os.path.join(image_dir,stims[trial])

                            my_image.draw() 
                            win.flip() 

                        win.close()
     
     #Results:
            Trial0 time = 2.0012667989940383
            Trial1 time = 2.0002630449889693
            Trial2 time = 2.0012952360266354

This shows that it is precise up to 2 decimal places. Sometimes it is accurate up to the third decimal place as you can see in 'Trial2 time'. 

2. 

                      
                                                
#Results:

            
