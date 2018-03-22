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
  
The | charecter known as *pipe*.the regular expression r'ABC|XYZ' will match either 'ABC' or 'XYZ'.

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
 

     
