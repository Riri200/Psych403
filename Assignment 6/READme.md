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
            
4. 

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
