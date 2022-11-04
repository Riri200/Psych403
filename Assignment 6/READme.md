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
