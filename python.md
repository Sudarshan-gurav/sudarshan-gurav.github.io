
### [Python_Assignment](https://sudarshan-gurav.github.io/Assignment)---[Steps to Install MySQL](https://sudarshan-gurav.github.io/Install_step)---[Basic_Concept about Database](https://sudarshan-gurav.github.io/Basic_concept)---[Basic Syntax of MySQL](https://sudarshan-gurav.github.io/Basic_Syntax) --- [Library Management Project](https://sudarshan-gurav.github.ioCreate_Insert) ---[Store Procedure in MySQL](https://sudarshan-gurav.github.io/store_procedure)---[Cursor in Store Procedure](https://sudarshan-gurav.github.io/cursor)---[steps to insatll oracle](https://sudarshan-gurav.github.io/step_install_oracle)[Python_Basic]---(https://sudarshan-gurav.github.io/python)




# Python Basic:

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
 
 > * import re
 
**Help page**

 > *  import re   #It is most important to import regular exression module.
 > *  help (re.match)
 > *  help (re)
      it just like man page in Linux.
      
 Since regular expressions frequently use backslashes in them, it is convenient to pass raw strings to the re.compile() function
 
 instead of typing extra backslashes. Typing r'\d\d\d-\d\d\d-\d\d\d\d' is much easier than 
 
 typing '\\d\\d\\d-\\d\\d\\d-\\d\\d\\d\\d'.
 
## Regular expressions can contain both special and ordinary characters.

**The special characters are:**
       
"."      :   Matches any character except a newline.
        
"^"      :   Matches the start of the string.

"$"      :   Matches the end of the string or just before the newline at
            the end of the string.
        
 "*"      :   Matches 0 or more (greedy) repetitions of the preceding RE.
                 Greedy means that it will match as many repetitions as possible.
       
 "+"      :  Matches 1 or more (greedy) repetitions of the preceding RE.
       
 "?"      :  Matches 0 or 1 (greedy) of the preceding RE.
       
 ?,+?,??  :  Non-greedy versions of the previous three special characters.
        
 {m,n}    :  Matches from m to n repetitions of the preceding RE.
        
 {m,n}?   :  Non-greedy version of the above.
        
 "\\"     : Either escapes special characters or signals a special sequence.
        
  []      : Indicates a set of characters.
                 A "^" as the first character indicates a complementing set.
       
 "|"        :  A|B, creates an RE that will match either A or B.
        
 (...)      :  Matches the RE inside the parentheses.
                 The contents can be retrieved or matched later in the string.
        
 ## Ordinory Charecter are
 
 \number  Matches the contents of the group of the same number.
 
 \A       Matches only at the start of the string.
 
 \Z       Matches only at the end of the string.
 
 \b       Matches the empty string, but only at the start or end of a word.
 
 \B       Matches the empty string, but not at the start or end of a word.
 
 \d       Matches any decimal digit; equivalent to the set [0-9].
 
 \D       Matches any non-digit character; equivalent to the set [^0-9].
 
 \s       Matches any whitespace character; equivalent to [ \t\n\r\f\v].
 
 \S       Matches any non-whitespace character; equiv. to [^ \t\n\r\f\v].
 
 \w       Matches any alphanumeric character; equivalent to [a-zA-Z0-9_].
                 With LOCALE, it will match the set [0-9_] plus characters defined
                 as letters for the current locale.
 
 \W       Matches the complement of \w.
 
 \\       Matches a literal backslash.
 
 
 ## Regular Expression Funtion
 
This module exports the following functions:
 
 **match**  
 
 Match a regular expression pattern to the beginning of a string.
 
 **search**   
 
 Search a string for the presence of a pattern.
 
 **sub**
 
 Substitute occurrences of a pattern found in a string.
 
 **subn**
 
 Same as sub, but also return the number of substitutions made.
 
 **split**
 
 Split a string by the occurrences of a pattern.
 
 **findall**
 
 Find all occurrences of a pattern in a string.
 
 **finditer**
 
 Return an iterator yielding a match object for each match.
 
 **compile**
 
 Compile a pattern into a RegexObject.
 
 **purge**
 
 Clear the regular expression cache.
 
 
 **escape**
 
 Backslash all non-alphanumerics in a string.

**NOTE :In Regular Expression '()' Parentheses is important.
 
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


                 
              #basic re it uses ' \ '

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

 returns a tuple of multiple values
 
**group()**

This method returns entire match (or specific subgroup num)
   
**Difference between match and search is only**

match checks for a match only at the beginning of the string, while search checks for a match anywhere in the string (this is what Perl does by default).

## Simple Login Form:

First Approach :

program simply check login detail.it check name and password varible if it is true then it would be print access granted

and if not then it will print wrong password but this approach work once.

Second Approach :

This Approach We use the while loop it will be check continuesoly the name and password is same or not.

```python

first Approach :
         name = 'sudarshan'
         password = 'admin123'
         name1 = input('enter the name: ')
         password1 = input('enter the password: ')
         if name == name1:
             print('welcome '+name)
         if password == password1:
                  print('access granted')
         else:
                 print('wrong password')
                 
-----------------------------------------------------------------------------------------------------------------------
 Second Approach :
 
      name = 'sudarshan'
       password = 'gurav'
       count = 0

       while True:
           name1 = input('enter the name: ')
           password1 = input('enter the password: ')
           if name == name1:
               print('welcome '+name)
               if password == password1:
                       print('access granted')
                       break
           else:
               print('wrong password')
               count +=1
               if (count == 3):
                   print('try after 5 min')
                   break
```
## Matching Multiple Groups with the Pipe ( | ):
  
  The (|) charecter known as *pipe*.the regular expression r'ABC|XYZ' will match either 'ABC' or 'XYZ'.

eg.
```python

   >>>name = re.compile(r'sudarshan|gurav')

   >>> find = name.search ('sudarshan and gurav')

   >>> find.group()
   
Out>>> 'sudarshan'


```
```python
 
    week = re.compile(r'(sun|mon|fri)day')
    findweek = week.search('is it sunday')
    findweek.group()
    
    #out>>> 'sunday'
    
```

When both *sudarshan and gurav* occur in the searched string, the *first* occurrence of matching text will be returned as the

Match object. 
 
**Optional Matching with the Question Mark**

 The regex will match text that has *zero instances or one instance* of *wo* in it. 
 
 This is why the regex matches both *'Batwoman' and 'Batman'.*
 
```python

  >>> rexes = re.compile(r'Bat(wo)?man')
  >>> find = rexes.search('the adventure of Batman')
  >>> find.group()
  'Batman'
  >>> find = rexes.search('the adventure of Batwoman')
  >>> find.group()
  'Batwoman'
  
```

**Matching Zero or More with the Star(*)**

  (*) means *“match zero or more”*

It can be completely absent or repeated over and over again.Let see example.

```python
      >>> rexes = re.compile(r'Bat(wo)*man')
      >>> find = rexes.search('the adventure of Batman')
      >>> find.group()
      'Batman'
      >>> find = rexes.search('the adventure of Batwoman')
      >>> find.group()
      'Batwoman'
      >>> find = rexes.search('the adventure of Batwowowowoman')
      >>> find.group()
      'Batwowowowoman'

```

**Matching One or More with the Plus**

  ( + ) (or plus) means *“match one or more.”*
 
```python



```

**Matching Specific Repetitions with Curly Brackets**

If we have a group that we want to repeat a specific number of times, follow the group in our regex with a number in curly 

brackets. 

For example, the regex (Hello){3} will match the string 'HelloHelloHello', but it will not match 'HelloHello', 

since the latter has only two repeats of the (Hello) group

Insted of one number.you can specify a range by writing a (minimum, maximum )in between the curly brackets. 

For example, the regex (Hello){3,5} will match 'HelloHello', 'HelloHelloHello', and 'HelloHelloHelloHelloHello'.

(Hello){3,} will match three or more instances of the (Hello) group, 

while (Hello){,5} will match zero to five instances. 

**Let see some example**

 ```python

                >>> import re
                >>> helloregex = re.compile(r'(hello){3}')
                >>> find = helloregex.search('hellohellohello')
                >>> find.group()
                'hellohellohello'
                >>> 
                >>> 
                >>> find = helloregex.search('hello')
                >>> find.group()
                Traceback (most recent call last):
                  File "<pyshell#8>", line 1, in <module>
                    find.group()
                AttributeError: 'NoneType' object has no attribute 'group'
                >>> find ==None
                True

```

**Greedy and Nongreedy Matching**

Python’s regular expressions are *greedy* by default, which means that in *ambiguous* situations they will match the *longest 

string* possible. The *non-greedy* version of the curly brackets, which matches the *shortest* string possible, has the closing 

curly bracket followed by a *question mark.*

  ```python

#Greddy        
        >>> greedyHelloRex = re.compile(r'(hello){3,5}')
        >>> regexe = greedyHelloRex.search('hellohellohellohellohello')
        >>> regexe.group()
        'hellohellohellohellohello'
       
        #Display Longest String
        
#Nongreddy

        >>> import re
        >>> nongreddy = re.compile(r'(hello){2,4}?')
        >>> regex = nongreddy.search('hellohellohellohello')
        >>> regex.group()
        'hellohello'

        #Display Shortest String 

```

**NOTE**
*The question mark can have two meanings in regular expressions: declaring a **nongreedy** match or **flagging** an optional 

group.*

## The findall() Method


While search() will return a Match object of the first matched text in the searched string, the findall() method will return the 

strings of every match in the searched string. 

**search()**

```python
           >>>import re
           >>> m = re.compile(r'\d{3}-\d{3}-\d{4}')
           >>> m1 = m.search('cell :123-320-3211 work :123-321-3121')
           >>> m1.group()

           '123-320-3211'

```
**findall()**

```python
         >>>import re
         >>> m = re.compile(r'\d{3}-\d{3}-\d{4}')
         >>> m.findall('cell :123-320-3211 work :123-321-3121')
         ['123-320-3211', '123-321-3121']

```
**Character Classes**

There are many such shorthand character classes

```python 

       >>>charecter = re.compile(r'\d+\s\w+')
       >>>charecter.findall('12 shree, 25 rajesh, 21 sanjay')
       
       #output['12 shree', '25 rajesh', '21 sanjay']
       
      ------------------------------------------------------------- 
      
      >>>ch =re.compile(r'\d+\s\w+\d+\w+')
      >>>ch.findall('122 sudarshan123admim')
      
      #output:['122 sudarshan123admim']
      
      -------------------------------------------------------------
      
      >>>ch =re.compile(r'\d+\s+\w+\s+\d+\s+\w+')
      >>>ch.findall('122 sudarshan 123 admim')
      
      #output:['122 sudarshan 123 admim']
      
      ------------------------------------------------------------
```

**Making Your Own Character Classes**

```python

         #OwnCharecter =re.compile(r'[enter string or number what we want to serach ]')
         
         >>>OwnCharecter =re.compile(r'[ABCabc]')
         >>>OwnCharecter.findall('as we know About That')
         #output:['a', 'A', 'b', 'a']
         
```

We can also include ranges of letters or numbers by using a hyphen. 

For example, the character class [a-z A-Z 0-9] will match all lowercase letters, uppercase letters, and numbers.

```python 
  
        >>> OwnCharecter.findall('as we know About That')
        ['a', 'A', 'b', 'a']
        >>> OwnCharecter =re.compile(r'[A-Z\sa-z\s0-9]')    #specify the range between
        >>> 
        >>> OwnCharecter.findall('Sudarshan Gurav')
        ['S', 'u', 'd', 'a', 'r', 's', 'h', 'a', 'n', ' ', 'G', 'u', 'r', 'a', 'v','9', '0', '9', '6', '6', '2', '2', '1', '7',                                   '9']
        
        
```
Inside the square brackets, the normal regular expression symbols are not interpreted as such. 

This means We do not need to escape the . , * , ?, or () characters with a preceding backslash.

Eg.[0-5\.]   # Not allow

placing a caret character (^) just after the character class’s opening bracket, We can make a negative character class.

A negative character class will match all the characters that are not in the character class. 

The belwo code check vowel inside string :

```python

  >>>vowel = re.complie(r'[aeiouAEIOU]')
  >>>vowel.findall('every developer as know the c language')
  
  #output :['e', 'e', 'e', 'e', 'o', 'e', 'a', 'o', 'e', 'a', 'u', 'a', 'e']

```
The belwo code ignore vowel inside string :

```python
     
      >>>vowel = re.complie(r'[^aeiouAEIOU]')  #use caret symbol
      >>>vowel.findall('every developer as know the c language')
    
      #output :['v', 'r', 'y', ' ', 'd', 'v', 'l', 'p', 'r', ' ', 's', ' ', 'k', 'n', 'w', ' ', 't', 'h', ' ', 'c', ' ', 'l',          'n', 'g', 'g']


```
**The Caret and Dollar Sign Characters**

1. caret symbol (^) at the start of a regex to indicate that a match must occur at the beginning of the searched text.

2. dollar sign ($) at the end of the regex to indicate the string must end with this regex pattern.


1.
```python

               >>> beginsHello = re.compile(r'^Hello')
               >>> beginsHello.search('Hello world!')
               <_sre.SRE_Match object; span=(0, 5), match='Hello'>

```
2.
```python

                      >>> endsNumber = re.compile(r'\d$')
                      >>> endsNumber.search('Your number is 42')
                      <_sre.SRE_Match object; span=(16, 17), match='2'>
```

The r'^\d+$' regular expression string matches strings that both begin and end with one or more numeric characters.

**The Wildcard Character**

The . (or dot) character in a regular expression is called a wildcard.

```python
     
      >>> reg.findall('the sunday and monday as we as friday')
       ['nday', 'nday', 'iday']
       
```

Remember that the dot character will match just one character.

**Matching Everything with Dot-Star**

We can use the dot-star (.* ) to stand in for that “anything.” Remember that the dot character means “any single character except

the newline,” and the star character means “zero or more of the preceding character.”

```python

            >>> name = re.compile(r'First name:(.*) Last name:(.*)') 
            >>>MatchEvery = name.search('First name:sudarshan Last_name:gurav')
            >>>MatchEvery.group(1) # sudarshan
            >>>MatchEvery.group(2) # gurav
            >>>MatchEvery.group() #  First name:sudarshan Last_name:gurav
            
            
            >>> nongreedyRegex = re.compile(r'<.*?>')
            >>> mo = nongreedyRegex.search('<That was awesome> experience in krishagni.>')
            >>> mo.group()
            '<That was awesome>'

            >>> greedyRegex = re.compile(r'<.*>')
            >>> mo = greedyRegex.search('<That was awesome> experience in krishagni.>')
            >>> mo.group()
            '<That was awesome> experience in krishagni.>'
            
        
```

**REVIEW**


    The ? matches zero or one of the preceding group.

    The * matches zero or more of the preceding group.

    The + matches one or more of the preceding group.

    The {n} matches exactly n of the preceding group.

    The {n,} matches n or more of the preceding group.

    The {,m} matches 0 to m of the preceding group.

    The {n,m} matches at least n and at most m of the preceding group.

    {n,m}? or *? or +? performs a nongreedy match of the preceding group.

    ^spam means the string must begin with spam.

    spam$ means the string must end with spam.

    The . matches any character, except newline characters.

    \d, \w, and \s match a digit, word, or space character, respectively.

    \D, \W, and \S match anything except a digit, word, or space character, respectively.

    [abc] matches any character between the brackets (such as a, b, or c).

    [^abc] matches any character that isn’t between the brackets.

**Case-Insensitive Matching**

regular expressions match text with the exact casing we specify. 

**Let see example of Case-Insensitive**

To make your regex case-insensitive, you can pass re.IGNORECASE or re.I as a second argument to re.compile().
```python 
     
     >>> var = re.compile(r'developer',re.I)
     >>> var.search('The krishagni Developer').group()
     'Developer'
     
     >>> var.search('The krishagni DEVELOPER').group()
     'DEVELOPER'

```
**Substituting Strings with the sub() Method**



# READING AND WRITING A FILE IN PYTHON


**Files and File Paths**

Windows, paths are written using backslashes (\) as the separator between folder names.
Linux, however, use the forward slash (/) as their path separator. 
os.path.join() function is helpful if you need to create strings for filenames. 
>>> import os
>>> 
>>> os.path.join('home','krishagni','Documents')
'home/krishagni/Documents'
>>> os.path.join('home','krishagni','XYZ')
'home/krishagni/XYZ'

joins names from a list of filenames to the end of a folder’s name:

>>> myfiles = ['demo.txt','sql.csv','function.c']
>>> for filename in myfiles:
	print(os.path.join('/home/krishagni',filename))
 
/home/krishagni/demo.txt
/home/krishagni/sql.csv
/home/krishagni/function.c

We can get the current working directory as a string value with the os.getcwd()  [Like $pwd] 

>>> os.getcwd()
'/home/krishagni'

This function and change it with os.chdir().

>>> os.chdir('/home/krishagni/Desktop')
>>> 
>>> os.getcwd()
'/home/krishagni/Desktop'

**Absolute vs. Relative Paths**

There are two ways to specify a file path.

    *An absolute path, which always begins with the root folder*

    *A relative path, which is relative to the program’s current working directory*

There are also the dot (.) and dot-dot (..) directory. These are not real directory but special names that can be used in a path. 

A single period (“dot”) for a directory name is shorthand for “this directory.” Two periods (“dot-dot”) means “the parent 

directory.”


E.g : Relative Path:
       
    > *     ./
    > *   ../
    > *   ../demo/file1.txt
  
E.g : Absolute path:

    > *  /etc/apache2/conf
    > *  /home/demo/file1.txt
    
  **Creating New Folders with os.makedirs()**
  
    >>> import os
    >>> os.makedirs('/home/krishagni/Desktop/new_creation')
 
**Handling Absolute and Relative Paths**

The os.path module provides functions for returning the absolute path of a relative path and for checking whether a given path is an absolute path.

    1.Calling os.path.abspath(path) will return a string of the absolute path of the argument. This is an easy way to convert a relative path into an absolute one.

    2.Calling os.path.isabs(path) will return True if the argument is an absolute path and False if it is a relative path.

    3.Calling os.path.relpath(path, start) will return a string of a relative path from the start path to path. If start is not provided, the current working directory is used as the start path.

		>>> os.path.abspath('.')
		'/home/krishagni/Desktop'
		>>>

		>>> os.path.abspath('./new_creation')
		'/home/krishagni/Desktop/new_creation'
		>>> 

		>>> os.path.isabs('.')
		False
		>>> 

		>>> os.path.isabs('/home')
		True
		>>> 

		>>> os.path.isabs(os.path.abspath('.'))
		True
		>>> 
     
     
     
Calling os.path.dirname(path) will return a string of everything that comes before the last slash in the path argument. 

Calling os.path.basename(path) will return a string of everything that comes after the last slash in the path argument.

E.g :
  
  > * /home/krishagni/Desktop/file.txt  [ /home/krishangni/Desktop ] is Dir_name [ file.txt ] is base_name
  
  
		   >>> path = ('/home/krishagni/input.txt')
		   >>> os.path.basename(path)
		   'input.txt'

		   >>> os.path.dirname(path)
		   '/home/krishagni'
		   >>> 


If you need a path’s dir name and base name together, you can just call os.path.split() to get a tuple value with these two strings, like so:


		>>>file_path = ('/home/krishagni/Desktop/input.txt')
		>>> os.path.split(file_path)
		('/home/krishagni/Desktop', 'input.txt')
		
os.path.split() does not take a file path and return a list of strings of each folder. For that, use the split() string method 

and split on the string in os.sep. Recall from earlier that the os.sep variable is set to the correct folder-separating slash for 

the computer running the program.

		>>> file_path.split(os.path.sep)
		['', 'home', 'krishagni', 'Desktop', 'input.txt']
		>>> 
		
**Finding File Sizes and Folder Contents**

1.Calling os.path.getsize(path) will return the size in bytes of the file in the path argument.

2'Calling os.listdir(path) will return a list of filename strings for each file in the path argument. (Note that this function is 

in the os module, not os.path.)

                 #get the size of directory  
		 #finding the size of a file in bytes and the files and folders inside a given folder.
		 
		>>> os.path.getsize('/home/krishagni/Desktop/')
		4096   # size of this directory
		
		#list of directory's like ls
		>>> os.listdir('/home/krishagni/Documents/openspecimen1/app')
		['openspecimen', 'openspecimen2', 'uninstall', 'openspecimen1', 'tomcat-as', '.install4j']
		>>> 


I have a lot of files in /home/krishagni/Desktop. If I want to find the total size of all the files in this directory, I can use 

os.path.getsize() and os.listdir() together.

		>>> for filename in os.listdir('/home/krishagni/Desktop/'):
			totalsize = totalsize + os.path.getsize(os.path.join('/home/krishagni/Desktop',filename))


		>>> print(totalsize)
		84443415
		>>> 
		
**The File Reading/Writing Process**

There are three steps to reading or writing files in Python.

 1.Call the open() function to return a File object.

 2.Call the read() or write() method on the File object.

 3.Close the file by calling the close() method on the File object.


**Opening Files with the open() Function**

      
      >>> helloFile = open('/Users/your_home_dir_path/fine_name.exetension')
      
      >>> open_input = open('/home/krishagni/Desktop/re.py')
      
  These commands will open the file in “reading plaintext” mode, or read mode for short. 
 
   The call to open() returns a File object. A File object represents a file on your computer
   
   **Reading the Contents of Files**
   
  1.read():reads the file as an individual string, and so allows relatively easy file-wide manipulations
  
  2.readline():reads a single line of the file, allowing the user to parse a single line without necessarily reading the entire   
   
  file
   
		   >>> open_input = open('/home/krishagni/Desktop/re.py')
   
		   >>> open_input = open_input.read()
		   >>> open_input
			"message = 'Hello World'"
	
------------------------------------------------------
Readline()

		>>> new = open('re.py')
		>>> new.readlines()
		["message = 'Hello World']

---------------------------------------------------------------------------

**Writing to Files**

If the filename passed to open() does not exist, both write and append mode will create a new, blank file. After reading or 

writing a file, call the close() method before opening the file again.

		>>> create = open('hello.txt','w')
		>>> 
		>>> create.write('added a new linw')
		16
		>>> 
		>>> create = open('hello.txt','a')
		>>> create.write('addind latest lines')
		19
		>>> create.close()
		
		>>> create = open('hello.txt')
		>>> 
		>>> contain = create.read()
		>>> create.close()
		
		>>> print(contain)
		added a new linwaddind latest lines
		
		
*Try to solve
Regex Search: Write a program that opens all .txt files in a folder and searches for any line that matches a user-supplied regular expression. The results should be printed to the screen.


# Organizing Files

**The shutil Module**

The shutil (or shell utilities) module has functions to let We copy, move, rename, and delete files in our Python programs. To 

use the shutil functions, we will first need to use import shutil.

**Copying Files and Folders**

Calling shutil.copy(source, destination) will copy the file at the path source to the folder at the path destination. (Both 

source and destination are strings.) If destination is a filename, it will be used as the new name of the copied file. This 

function returns a string of the path of the copied file.

```python

			>>> import shutil,os
			>>> os.chdir('/')
			>>> shutil.copy('/home/krishagni/Desktop/hello.txt','/home/krishagni/Documents')
			'/home/krishagni/Documents/hello.txt'

```
While shutil.copy() will copy a single file, shutil.copytree() will copy an entire folder and every folder and file contained in it. Calling shutil.copytree(source, destination) 

The shutil.copytree() call creates a new folder named demo with the same content as the original git-repo folder.
demo
```python

		>>> shutil.copytree('/home/krishagni/Desktop/git-repo','/home/krishagni/Documents/demo')
		'/home/krishagni/Documents/demo'
		>>> 
		
```

**Moving and Renaming Files and Folders**

Calling shutil.move(source, destination) will move the file or folder at the path source to the path destination and will return 

a string of the absolute path of the new location.

If destination points to a folder, the source file gets moved into destination and keeps its current filename


```python

		>>> import shutil, os
		>>> 
		>>> shutil.move('/home/krishagni/Desktop/openspecimen_v5.0.b22_EE.zip','/home/krishagni/Documents/openspecimen1/.')
		'/home/krishagni/Documents/openspecimen1/./openspecimen_v5.0.b22_EE.zip'
		>>> 
		>>> shutil.move('/home/krishagni/Documents/openspecimen1/openspecimen_v5.0.b22_EE.zip','/home/krishagni  /Documents/openspecimen1/installble/')
		'/home/krishagni/Documents/openspecimen1/installble/openspecimen_v5.0.b22_EE.zip'
		>>> 
		
```		


The destination path can also specify a filename. In the following example, the source file is moved and renamed.

```python

	>>> shutil.move('/home/krishagni/Desktop/demo.txt, '/home/krishagni/Documents/new_demo.txt')
	   '/home/krishagni/Document/new_file.txt'

```

**Permanently Deleting Files and Folders**

1.Calling os.unlink(path) will delete the file at path.

2.Calling os.rmdir(path) will delete the folder at path. This folder must be empty of any files or folders.

3.Calling shutil.rmtree(path) will remove the folder at path, and all files and folders it contains will also be deleted.

```python

		>>> os.chdir('/home/krishagni/')
		>>> 
		>>> os.getcwd()
		'/home/krishagni'
		>>> for filename in os.listdir():
			if filename.endswith('.txt'):
				#os.unlink(filename)
				print(filename)


		tempdata.txt
		input.txt
		doc.txt
		exampleout.txt
		
		>>> for filename in os.listdir():
			if filename.endswith('.txt'):
				os.unlink(filename)
				print(filename)


		tempdata.txt
		input.txt
		doc.txt
		exampleout.txt
		>>> for filename in os.listdir():
			if filename.endswith('.txt'):
				#os.unlink(filename)
				print(filename)


		>>>#4 file's are delete paramently

```

**Walking a Directory Tree**

os.walk() function 

	for folderName in os.walk('/home/krishagni/Desktop/'):
             print('The current folder is ' + folderName)
   
       # it will diplay all folder and subfolder inside of Desktop directory.
       
  **Compressing Files with the zipfile Module**
  
 To create a ZipFile object, call the zipfile.ZipFile() function, passing it a string of the .zip file’s filename. Note that 
 
 zipfile is the name of the Python module,
  
```python
			
			>>> contain_zip = zipfile.ZipFile('openspecimen_v5.0.b22_EE.zip')
			>>> 
			>>> contain_zip.namelist()

                        #it display all contain inside Zip file.
```

A Zip file has it namelist() object



# Debugging

**Raising Exceptions**

Exceptions are raised with a raise statement. In code, a raise statement consists of the following:

1 The raise keyword

2 A call to the Exception() function

3 A string with a helpful error message passed to the Exception() function

If there are no try and except statements covering the raise statement that raised the exception, the program simply crashes and 

displays the exception’s error message.


**Using the logging Module**

To enable the logging module to display log messages on your screen as your program runs, copy the following to the top of your program (but under the #! python shebang line):

```python

		import logging
		logging.basicConfig(level=logging.DEBUG, format=' %(asctime)s - %(levelname)s - %(message)s')
```



it creates a LogRecord object that holds information about that event. The logging module’s basicConfig() function lets you 

specify what details about the LogRecord object you want to see and how you want those details displayed.

Here we can see simple program of logging :

```python
		import logging
		logging.basicConfig(level=logging.DEBUG, format=' %(asctime)s - %(levelname)s - %(message)s')
		logging.debug('Start of program')

		list1 =  ['a','b','c','d']

		for i in list1:
		    logging.debug('i value is ' + str(i))
		    print(list1)

              output:
	      
	         2018-03-23 16:57:33,644 - DEBUG - Start of program
		 2018-03-23 16:57:33,653 - DEBUG - i value is a
		['a', 'b', 'c', 'd']
		 2018-03-23 16:57:33,663 - DEBUG - i value is b
		['a', 'b', 'c', 'd']
		 2018-03-23 16:57:33,674 - DEBUG - i value is c
		['a', 'b', 'c', 'd']
		 2018-03-23 16:57:33,684 - DEBUG - i value is d
		['a', 'b', 'c', 'd']
		
		>>> 
```

**Don’t Debug with print()**

Typing import logging and logging.basicConfig(level=logging.DEBUG, format= '%(asctime)s - %(levelname)s - %(message)s') is 

somewhat unwieldy. You may want to use print() calls instead, but don’t give in to this temptation! Once you’re done debugging, 

you’ll end up spending a lot of time removing print() calls from your code for each log message

**Logging Levels**

I will provide a link for Table of logging level in python:

https://docs.google.com/document/d/1Yr6Vm5fTUQNZcpelT3szKqaR6L1kvIwphUDm4-sQ09U/edit#


E.g

```python
		>>> import logging
		>>> logging.basicConfig(level=logging.DEBUG, format =' %(asctime)s - %(levelname)s - %(message)s')
		>>> logging.debug('debuging details')
		 2018-03-23 17:22:13,853 - DEBUG - debuging details
		>>> logging.info('The module is working')
		 2018-03-23 17:23:11,997 - INFO - The module is working
		>>> logging.warning('error about the log')
		 2018-03-23 17:24:19,581 - WARNING - error about the log
		>>> logging.error('An error has occurred.')
		 2018-03-23 17:24:28,469 - ERROR - An error has occurred.
		>>> logging.critical('The program is unable to recover!')
		 2018-03-23 17:24:34,700 - CRITICAL - The program is unable to recover!
		>>> 
```
**Logging to a File**

Instead of displaying the log messages to the screen, you can write them to a text file. The logging.basicConfig() function takes a filename keyword argument, like so:

```python

	import logging
	logging.basicConfig(filename='myProgramLog.txt', level=logging.DEBUG, format='
	%(asctime)s - %(levelname)s - %(message)s')

```
The log messages will be saved to myProgramLog.txt. While logging messages are helpful.

**Breakpoints**

A breakpoint can be set on a specific line of code and forces the debugger to pause whenever the program execution reaches that 

line. 

**In Pyhon IDLE:**

To set a breakpoint, right-click the line in the file editor and select Set Breakpoint.

# Web Scraping

