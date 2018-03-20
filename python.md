Install Ipython in linux :
 
     It provide facility of TAB using to complate the word just like linux.
     
    > * sudo apt install ipython

**What is dictionary in Python?**

Python dictionary is an unordered collection of items. While other compound data types have only value as an element, 

a dictionary has a key: value pair.

**How to create a dictionary?**

Creating a dictionary is as simple as placing items inside curly braces *{}* separated by comma.

An item has a key and the corresponding value expressed as a pair, key: value.*key must be unique*

Diffrenece between LIST and TUPLE:

**LIST:**

 The contain of list may be change.
 
 eg. list1=['a','b']
 
 **TUPLE:**
  
   The contain of tuple may not changed.
        *it is actually comma ehich is make a tuple not the parentheses.*
        
  eg. tup1 = 'a', 'b', 'c'
    
 **What is Module?**
      
 **Using re.match()**
  
   It take two input 
   "a regex " and "things to match against"
   It return NONE or match object
   
 **Regular Expression**
 
 A regular expression is a special sequence of characters that helps you match or find other strings or sets of strings, using a 
 specialized syntax held in a pattern.
   
 Regular expression is also known as *regexes*.
   
 a \d in a regex stands for a digit character—that is, any single numeral 0 to 9. 
   
 **Creating Regex Objects** 
 
 All regexes function in python are in the *re* module
 
 >>> import re
 
 **Help page**
 
 > * help (re.match)
 > * help (re)
      it just like man page in Linux.
      
 Since regular expressions frequently use backslashes in them, it is convenient to pass raw strings to the re.compile() function
 
 instead of typing extra backslashes. Typing r'\d\d\d-\d\d\d-\d\d\d\d' is much easier than 
 
 typing '\\d\\d\\d-\\d\\d\\d-\\d\\d\\d\\d'.
 
 
## Let,see same basic regular expression example and Method on regexes

> * help (re) this command give's a all information about re module

 ```python
               import re


             syntax: search(pattern, string, flags=0)
                      Scan through string looking for a match to the pattern, returning
                      a match object, or None if no match was found.
              ----------------------------------------------------------------------------        

              if re.search ("information", "we need the latest information"):
                  print("their is inform")

              else:

                   print("not found")

              ----------------------------------------------------------------------------
              


              syntax : findall(pattern, string, flags=0)
                      Return a list of all non-overlapping matches in the string

              findStr = re.findall("hello "," hello world")

               #it find need word in string 

              for i in findStr:
                  print(i)

              ---------------------------------------------------------------------------
             
            
              syntax :finditer(pattern, string, flags=0)
                      Return an iterator over all non-overlapping matches in the
                      string.  For each match, the iterator returns a match object.


              str = 'my name is sudarshan gurav and i am currently working in krishagni solution private limited'

              for i  in re.finditer("i",str):

                  tup1 = i.span()

                  print(tup1)

              -----------------------------------------------------------------------------
              
              


              str = "sday ,mday ,thueday , wensday , tday , friday ,saturday "

              allstr = re.findall ("[smtw]day",str)

              for i in allstr:

                  print(i)


                 
              ''' basic re it uses ' \ '

              number = re.findall(r'\d','my mob no is 9096622179')

              print('only number'+str(number))

              number = re.findall(r'\W','my mob no is 9096622179')

              print('it remove all word and number from string '+str(number))

              number = re.findall(r'\w','my mob no is 9096622179')

              print('it display number as well as word '+str(number))

              number = re.findall(r'\D','my mob no is 9096622179')

              print('it dispaly only word having in string '+str(number)) #remove number from existing string


              
              # re module with match method :
              
              syntax:match(pattern, string, flags=0)
                      Try to apply the pattern at the start of the string, returning
                      a match object, or None if no match was found.

              str1 = 'sudarshan gurav'

              matchs=re.match('sudarshan' , str1)

              print(matchs)   # match method serach only first position of string

              # output: span=(0, 9), match='sudarshan'

              str1 = 'sudarshan gurav'

              matchs=re.match('gurav' , str1)

              print(matchs)  # no word found in the first place

               output : None

              
              # re module with search method :

              
              str1 = 'sudarshan gurav'

              matchs=re.search('gurav' , str1)

              print(matchs)  # this method search the whole string then give result

              #output : span=(10, 15), match='gurav'
              
              --------------------------------------------------------------------------------------------
              
            phonenumber =re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')

            mobile_number = phonenumber.search('my number is 909-662-2179')

            print(mobile_number.group(1))

            print(mobile_number.group(2))

            print(mobile_number.group(0)) # it retrive all the group
            
            print(mobile_number.groups())

            #output : 909
            #         662-2179
            #         909-662-2179
            #         ('909-662-2179',)
            
            

                
```
**groups()**

This method returns all matching subgroups in a tuple.

**group()**

This method returns entire match (or specific subgroup num)
   
