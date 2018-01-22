### Queation : Count the occurrences of every word in an input file (Python) 

Input       : *Apple is healthy food. Soda is junk food.*

Output      : 

*Apple       : 1*  

*is          : 2*

*healthy     : 1*

*food        : 2*

*Soda        : 1*

*junk        : 1*

**Description : first approch it take more time to count number of occurrences in that program i have use regular expression**

**Author      : Krishagni solution private limited.**

**Date        : 16/01/2018.**

**version     : KSPL V1.0.**
**About Approach : 
              
 
   
   
    ''' import re,string,time

     start=time.time()

     def makechunk(filer,size=30000000):
       while True:
         data=filer.read(size).lower()
         if data:
           yield data
       else:
           break
       
    Dictionary = {}

    file=open('Output.txt','w')
    file=open('Output.txt','a')

    file_read = open('1gb.txt', 'r')

    for d in makechunk(file_read):
        match=d.split(' ')
        for word in match:
            count = Dictionary.get(word,0)
            Dictionary[word] = count + 1
   
    for k,v in Dictionary.items():
        text="* "+k+": "+str(v)+"\n"
        file.write(text)
   
    file.close()
    print("* Execution time : {} sec *".format(time.time()-start))
    '''


**Author      : Krishagni solution private limited.**

**Description : second approch it take less time as compare to first approach to count number of occurrences without using prepared statement**

**Backend     : sqlite3**

**Date        : 17/01/2018.**

**version     : KSPL V2.0**



    '''     
        import time,sqlite3
	start=time.time()

	db = sqlite3.connect('new.db')
	cursor = db.cursor()
	db.commit()

	print('connection establish sucessfully')
	
	def drop():
   	cursor.execute('drop table dict_data')
   
	def create_db():
   	cursor.execute('create table dict_data(name Text unique,value int)')
	print('table create sucessfully')

	def makechunk(filer,size=10000):
   	while True:
       	   data=filer.read(size).lower()
           if data:
           	yield data
       	  else:
          	 break
       
	Dictionary = {}

	file_read = open('10MB.txt', 'r')

	for d in makechunk(file_read):
   	    match=d.split(' ')
            for word in match:
       		count = Dictionary.get(word,0)
       		Dictionary[word] = count + 1
	
	def update_dict():
	for k,v in Dictionary.items():
     	    cursor.execute('update dict_data set value = value+? where name = ?',(v,k))
      	    if cursor.rowcount == 0:
                     cursor.execute('insert into dict_data(name,value) values (?,?)',(k,v))
        print('dict update sucessfully')  

	drop()
	create_db()
	update_dict()
	
	print(" Execution time : {} sec ".format(time.time()-start))

	db.commit()
	cursor.close()
	db.close()
	'''
**Author      : Krishagni solution private limited.**

**Description : Third approch it take less time as compare to second approach to count number of occurrences using prepared statement**

**Backend     : sqlite3**

**Date        : 17/01/2018.**

**version     : KSPL V3.0**

'''
	
	import time,sqlite3
	start=time.time()

	db = sqlite3.connect('dummy.db')
	cursor = db.cursor()
	db.commit()

	print('connection establish sucessfully')


	def drop():
 	    cursor.execute('drop table dict1')
  	    print('drop the table sucessfully')
   
	def create_db():
 	    cursor.execute('create table dict1(name Text unique,value int)')

   	print('table create sucessfully')

	def chunk_call(fileread,size=1000000):
   	while True:
   	    data=fileread.read(size).lower()
     	  if data:
     	      yield data
      	 else:
              break
       
	Dictionary = {}

	file_read = open('10MB.txt', 'r')

	for data in chunk_call(file_read):
  	match=data.split(' ')
   	for word in match:
       	    count = Dictionary.get(word,0)
            Dictionary[word] = count + 1

	def update_dict():
   	list1=[]
       for key, value in Dictionary.items():
       list1 += [(value,key)]
	
       cursor.executemany('update dict1 set value = value + ? where name = ?',(list1))
       if cursor.rowcount == 0:
          cursor.executemany('insert into dict1(value,name) values (?,?)',(list1))

       db.commit()
       print('dict update sucessfully')
       del  list1[:]
       Dictionary.clear()            
       print('Dictionary clear sucessfully ')
      
       drop()
       create_db()
       update_dict()
                
       print(" Execution time : {} sec".format(time.time()-start))
     
       db.commit()
       cursor.close()
       db.close()

     '''

