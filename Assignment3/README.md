Answers to variable operations exercises:

1. print(sub_code+subnr_str) will create the output "sub2". Can not do print(sub_code+subnr_int) because subnr_int is an integer. 
2.
#sub 2    
print(sub_code+" "+subnr_str)


#sub 222       
print(sub_code+" "+(subnr_str*3))


#sub2sub2sub2       
print((sub_code+subnr_str)*3)


#subsubsub222      
print(sub_code*3+subnr_str*3) 



Answers to list operations exercises:

1. print(numlist*2)
2. print(numarr*2)      
Multiplying lists duplicated the list while multiplying arrays doubled the values. 
3. 
#['dodo','rere','mimi','fafa']         
print([strlist[0]*2,strlist[1]*2,strlist[2]*2,strlist[3]*2])

#['do','re','mi','fa','do','re','mi','fa']        
print(strlist*2)

#['do','do','re','re','mi','mi','fa','fa']       
print([strlist[0],strlist[0],strlist[1],strlist[1],strlist[2],strlist[2],strlist[3],strlist[3]])

#[['do','do'],['re','re'],['mi','mi'],['fa','fa']]          
print([[strlist[0],strlist[0]],[strlist[1],strlist[1]],[strlist[2],strlist[2]],[strlist[3],strlist[3]]])



Answers to zipping exercises:

1. catimgs=list(zip(first_item,second_item,cues))



Answers to indexing exercises:

1. colours=['red','orange','yellow','green','blue','purple']
2. print(colours[-2])
3. print(colours[-2][2])        
print(colours[-2][-3])
4. colours[-1]='indigo'        
colours.append('violet')



Answers to slicing exercises:

1. list100=list(range(101))
2. print(list100[:10])
3. temp=list100[1::2]        
print(temp[::-1])
4. temp=list100[-4:]        
print(temp[::-1])
5. print(list100[39:44]==[39,40,41,42,43])     
Yes, they are equal. 
