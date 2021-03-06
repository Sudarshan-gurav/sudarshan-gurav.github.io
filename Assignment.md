
### [Back To Link Page..](https://sudarshan-gurav.github.io/link)

# Python_Task:

### Question : Count the occurrences of every word in an input file (Python) 

Input       : *Apple is healthy food. Soda is junk food.*

Output      : 

*Apple       : 1*  

*is          : 2*

*healthy     : 1*

*food        : 2*

*Soda        : 1*

*junk        : 1*

 **Approch**

By looking at the question first thought that came to my mind is to use Dictionary, because dictionary contains a key-value pair.But since we have large files using dictionary can get a memory error.It is not possible to store huge data in dictionary
So instead of using dictionary we could use a .csv file but we want to count the occurrence of a word, we have to traverse the whole file and search that word and increment their value so it takes more time.
So the final approach was to use a database because using database we can easily traverse database,update and insert the word and their values. I used sqlite3 module to do all the database operations.

 **Prerequisite :** 
 
 -  Basic SQL knowledge.
 
 -  Transaction management.
 
 -  Prepared Statement.
 
 **Author      : Krishagni solution private limited.**

**Description : count the occurrences of every word  without using prepared statement**

**Backend     : sqlite3**

**Date        : 17/01/2018.**

**version     : KSPL V1.0**


# Program 

```python

        import time,sqlite3
	start=time.time()

	db = sqlite3.connect('new.db')
	cursor = db.cursor()
	db.commit()                        # This method commits the current transaction

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
           	yield data                       #yield statement is used to define generators
       	  else:
          	 break
       
	Dictionary = {}

	file_read = open('text_file.txt', 'r')

	for data in makechunk(file_read):
   	    match=data.split(' ')
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
```



**Description :  Count the occurrences of every word using prepared statement**

**Backend     : sqlite3**

**Date        : 17/01/2018.**

**version     : KSPL V2.0**


# Program 

```python
	
	import time,sqlite3

	start=time.time()

	db = sqlite3.connect('prepared.db')
	cursor = db.cursor()
	db.commit()

	print('connection establish sucessfully')	
	def drop():
   	   cursor.execute('drop table dict1')
           db.commit()
           print('drop the table sucessfully')
   
       def create_db():
           cursor.execute('create table dict1(name Text unique,value int)')
           db.commit()
           print('table create sucessfully')

       def chunk(fileread,size=30000000):
          while True:
              data=fileread.read(size).lower()
              if data:
                  yield data
              else:
                   break
	
       def update_db():
          list1=[]
          for key, value in dictionary.items():
              list1 += [(value,key)]
          cursor.executemany('update dict1 set value = value + ? where name = ?',(list1))
          try:
              cursor.executemany('insert into dict1(value,name) values (?,?)',(list1))
          except sqlite3.IntegrityError:
              print("",end='')
      db.commit()
      del  list1[:]
 
      Dictionary = {}
      drop()
      create_db()
       
      file_read = open('text_file.txt', 'r')
      for data in chunk(file_read):
          match=data.split(' ')
          for word in match:
               count = Dictionary.get(word,0)
               Dictionary[word] = count + 1
          update_db()
          Dictionary.clear()

       
      db.commit()
      cursor.close()
      db.close()
      print("***** Execution time : {} sec ******".format(time.time()-start))

```
# Execution Flow :
1.  import modules 
2.  create connection with sqlite3
3.  create table to store word and occurrence.
4.  after creating table read the file in chunk.
5.  split the word until space is found and store into the list(.split())
6.  iterate the loop on the size of the list.
7.  update the dictionary for each item.
8.  update_db() method is called then convert the dictionary into a list of tuples and pass that into executemany()method.
9.  If a word already exists then update its value into the database.
10. if word does not exist in database then insert the word and its value into the database.
11. make the dictionary empty and ready for a new chunk. 
12. Repeat.


