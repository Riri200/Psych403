**Answers to Psychopy Keypress Exercise**

1. 

    keys = event.getKeys(keyList=['1','2'])
    if keys:
        sub_resp = keys[0] 
        
    print(sub_resp)

2. 

When event.ClearEvents is within the trial loop, it will start a new key collection from where event.ClearEvents is placed and not record any responses prior to it.
When event.ClearEvents is outside the trial loop, it will not start a new key collection. 
When I unindent the "if keys:" line an Indentation Error occurs, which will not allow me to run the experiment. 

**Answers to Recording Data Excercises**

1.

    my_dict = {"KeyName":[],"SubjectRT":[],"SubjectAccuracy":[],"CorrectResp":[]}

    my_dict["KeyName"].append()
    my_dict["SubjectRT"].append()
    my_dict["SubjectAccuracy"].append()
    my_dict["CorrectResp"].append()
    
2.

    import numpy as np

    nBlocks=2
    nTrials=4

    corr_resp = [[0]*nTrials]*nBlocks
    prob = [[0]*nTrials]*nBlocks

    for block in range(nBlocks):
         prob[trial] = prob_sol[np.random.choice(1)]
         corr_resp[block][trial] = prob[block][1]
     
**Answer to Save CSV Exercise**     

    import csv 

    filename = 'savecsv_example.csv'
    print(filename)

    import os
    main_dir = os.getcwd() 

    data_dir = os.path.join(main_dir,filename)
    print(data_dir)

    my_dict = {"KeyName":[],"SubjectRT":[],"SubjectAccuracy":[],"CorrectResp":[]}

    with open(data_dir, mode='w') as sub_data:
        #delimiter=',' for lists of values separated by commas
        data_writer = csv.writer(sub_data, delimiter=',')
        data_writer.writerow(my_dict) 
        
**Answers to Loading CSV Exercise**

1.

    import pandas as pd

    df=pd.read_csv('/Applications/image/savecsv_example.csv')
    print(df)

    mean = df['SubjectAccuracy'].mean()
    print(mean)
   
   
