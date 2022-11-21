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

                        trial_timer = core.Clock() 

                        for trial in range(nTrials):
                                trial_timer.reset()
                                #-draw stimulus
                                my_image.draw()
                                while trial_timer.getTime()<=2:
                                    print('Trial'+str(trial)+' time =', trial_timer.getTime())
                                    my_image.image = os.path.join(image_dir,stims[trial])
                                    my_image.draw() 
                                    win.flip() 

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

                        pres_timer = core.CountdownTimer() 

                        for trial in range(nTrials):
                                pres_timer.reset()
                                pres_timer.add(2)
                                my_image.draw()
                                while pres_timer.getTime() >0:
                                    print('Trial'+str(trial)+' time =', pres_timer.getTime())
                                    my_image.image = os.path.join(image_dir,stims[trial])
                                    my_image.draw() 
                                    win.flip() 

                        win.close()
                        
#Results: 

            Trial0 time = 1.9997901470051147
            Trial1 time = 1.9996586630004458
            Trial2 time = 1.9997441659797914
            
Stimuli were presented roughly 1.999 seconds. This was more precise than clock_wait_timer. 

4. 

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
            nBlocks=2
            my_image = visual.ImageStim(win,units="pix",size=(400,400))

            trial_timer = core.Clock() 
            block_timer = core.Clock()

            for block in range(nBlocks):
                block_timer.reset() 

                for trial in range(nTrials):
                    trial_timer.reset()
                    my_image.draw()
                    while trial_timer.getTime()<=2:
                        print('Trial'+str(trial)+' time =', trial_timer.getTime())
                        my_image.image = os.path.join(image_dir,stims[trial])
                        my_image.draw() 
                        win.flip() 
                print('Block'+str(block)+' time =', block_timer.getTime())

            win.close()
            
**Answers to Frame-based Timing Excercises**   

1. 

            from psychopy import visual, monitors, event, core

            mon = monitors.Monitor('myMonitor', width=30, distance=57)
            mon.setSizePix([1024,768])
            win = visual.Window(monitor=mon) 

            import os
            os.chdir('/Applications')
            main_dir = os.getcwd() 
            image_dir = os.path.join(main_dir,'image')

            refresh=1.0/60.0

            fix_dur = 0.2 
            image_dur = 0.1 
            text_dur = 0.2 

            fix_frames = int(fix_dur / refresh) #whole number
            image_frames = int(image_dur / refresh) #whole number
            text_frames = int(text_dur / refresh) #whole number
            total_frames = int(fix_frames + image_frames + text_frames)

            import numpy as np 
            stims = ['face01.jpg','face02.jpg','face03.jpg'] 
            nTrials=3 
            nBlocks=2
            my_image = visual.ImageStim(win,units="pix",size=(400,400))

            trial_timer = core.Clock() 
            block_timer = core.Clock()

            for frameN in range(total_frames):
                if 0 <= frameN <= fix_frames:
                    win.flip()

                    if frameN == fix_frames:
                        print("End fix frame =", frameN)

                if fix_frames < frameN <= (fix_frames+image_frames):
                    win.flip()

                    if frameN == (fix_frames+image_frames):
                        print("End image frame =", frameN)

                if (fix_frames+image_frames) < frameN < total_frames:
                    win.flip()

                    if frameN == (total_frames-1):
                        print("End text frame =", frameN)

            win.close()
            

2. 

            from psychopy import visual, monitors, event, core, logging

            mon = monitors.Monitor('myMonitor', width=30, distance=57)
            mon.setSizePix([1024,768])
            win = visual.Window(monitor=mon) 

            import os
            os.chdir('/Applications')
            main_dir = os.getcwd() 
            image_dir = os.path.join(main_dir,'image')

            refresh=1.0/60.0

            fix_dur = 0.2 
            image_dur = 0.1 
            text_dur = 0.2 

            fix_frames = int(fix_dur / refresh) #whole number
            image_frames = int(image_dur / refresh) #whole number
            text_frames = int(text_dur / refresh) #whole number
            total_frames = int(fix_frames + image_frames + text_frames)

            import numpy as np 
            stims = ['face01.jpg','face02.jpg','face03.jpg'] 
            nTrials=3 
            nBlocks=2
            win.recordFrameIntervals = True
            win.refreshThreshold = 1.0/60.0 + 0.004
            logging.console.setLevel(logging.WARNING)

            my_image = visual.ImageStim(win,units="pix",size=(400,400))

            trial_timer = core.Clock() 
            block_timer = core.Clock()

            for frameN in range(total_frames):
                if 0 <= frameN <= fix_frames:
                    win.flip()

                    if frameN == fix_frames:
                        print("End fix frame =", frameN)

                if fix_frames < frameN <= (fix_frames+image_frames):
                    win.flip()

                    if frameN == (fix_frames+image_frames):
                        print("End image frame =", frameN)

                if (fix_frames+image_frames) < frameN < total_frames:
                    win.flip()

                    if frameN == (total_frames-1):
                        print("End text frame =", frameN)
            print('Overall, %i frames were dropped.' % win.nDroppedFrames)

            win.close()
            
Overall, 0 frames were dropped.            
