<html>
    <body>
      <h2>Queation : Count the occurrences of every word in an input file (Python) </h2>
        
       <b> Input <b>  : Apple is healthy food. Soda is junk food.
        
       <b> Output <b> :  Apple   : 1
                   is      : 2
                   healthy : 1
                   food    : 2
                   Soda    : 1
                   junk    : 1
       <code>
       import re,string,time

start=time.time()

def makechunk(filer,size=30000000):
   while True:
       data=filer.read(size).lower()
       if data:
           yield data
       else:
           break
       
frequency = {}

file=open('Output.txt','w')
file=open('Output.txt','a')

file_read = open('1gb.txt', 'r')

for d in makechunk(file_read):
   match=d.split(' ')
   for word in match:
       count = frequency.get(word,0)
       frequency[word] = count + 1
   
for k,v in frequency.items():
   text="* "+k+": "+str(v)+"\n"
   file.write(text)
   
file.close()
print("* Execution time : {} sec *".format(time.time()-start))
       </code>
      
  
       <p> To solve the above problem we have better knowledge in SQL.</p>
        prerequisist :
        1.how to connect 
      
      </body>
 
  </html>
