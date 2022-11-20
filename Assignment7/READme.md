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

                        from psychopy import visual, monitors, event, core

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

                        trial_timer = core.Clock() #define the clock at the beginning of the experiment

                        for trial in range(nTrials):
                                #-set stimuli and stimulus properties for the current trial 
                                #...  
                                #reset stimulus presentation timer right before the first stimulus should appear
                                trial_timer.reset()
                                #-draw stimulus
                                my_image.draw()
                                while trial_timer.getTime()<=2:
                                    print('Trial'+str(trial)+' time =', trial_timer.getTime())
                                    my_image.image = os.path.join(image_dir,stims[trial])
                                    my_image.draw() #draw
                                    win.flip() #show

                        win.close()
                      
                                                
#Results:
                       
             Trial0 time = 1.9879298160085455
             Trial1 time = 1.9829937450122088
             Trial2 time = 1.983276755985571            

Stimuli were presented roughly 1.98 seconds. Was not as precise as core.wait. 

3. 

                        from psychopy import visual, monitors, event, core

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

                        pres_timer = core.CountdownTimer() #define the clock at the beginning of the experiment

                        for trial in range(nTrials):
                                #-set stimuli and stimulus properties for the current trial 
                                #...  
                                #reset stimulus presentation timer right before the first stimulus should appear
                                pres_timer.reset()
                                pres_timer.add(2)
                                #-draw stimulus
                                my_image.draw()
                                while pres_timer.getTime() >0:
                                    print('Trial'+str(trial)+' time =', pres_timer.getTime())
                                    my_image.image = os.path.join(image_dir,stims[trial])
                                    my_image.draw() #draw
                                    win.flip() #show

                        win.close()
                        
#Results: 

            Trial0 time = 1.9997901470051147
            Trial1 time = 1.9996586630004458
            Trial2 time = 1.9997441659797914
            
Stimuli were presented roughly 1.999 seconds. This was more precise than clock_wait_timer. 

4. 

