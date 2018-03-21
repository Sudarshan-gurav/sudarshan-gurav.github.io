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

 > *  >>>import re   #It is most important to import regular exression module.
 > *  >>> help (re.match)
 > *  >>>help (re)
      it just like man page in Linux.
      
 Since regular expressions frequently use backslashes in them, it is convenient to pass raw strings to the re.compile() function
 
 instead of typing extra backslashes. Typing r'\d\d\d-\d\d\d-\d\d\d\d' is much easier than 
 
 typing '\\d\\d\\d-\\d\\d\\d-\\d\\d\\d\\d'.
 
## Regular expressions can contain both special and ordinary characters.

**The special characters are:**
       
"."      Matches any character except a newline.
        
"^"      Matches the start of the string.

"$"      Matches the end of the string or just before the newline at
         the end of the string.
        
 "*"      Matches 0 or more (greedy) repetitions of the preceding RE.
                 Greedy means that it will match as many repetitions as possible.
       
 "+"      Matches 1 or more (greedy) repetitions of the preceding RE.
       
 "?"      Matches 0 or 1 (greedy) of the preceding RE.
       
 ?,+?,?? Non-greedy versions of the previous three special characters.
        
 {m,n}    Matches from m to n repetitions of the preceding RE.
        
 {m,n}?   Non-greedy version of the above.
        
 "\\"     Either escapes special characters or signals a special sequence.
        
  []       Indicates a set of characters.
                 A "^" as the first character indicates a complementing set.
       
 "|"      A|B, creates an RE that will match either A or B.
        
 (...)    Matches the RE inside the parentheses.
                 The contents can be retrieved or matched later in the string.
        
 ## Ordinory Charecter are**
 
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
 
 
 **Regular Expression Funtion**
 
This module exports the following functions:
 
 match    Match a regular expression pattern to the beginning of a string.
 
 search   Search a string for the presence of a pattern.
 
 sub      Substitute occurrences of a pattern found in a string.
 
 subn     Same as sub, but also return the number of substitutions made.
 
 split    Split a string by the occurrences of a pattern.
 
 findall  Find all occurrences of a pattern in a string.
 
 finditer Return an iterator yielding a match object for each match.
 
 compile  Compile a pattern into a RegexObject.
 
 purge    Clear the regular expression cache.
 
 escape   Backslash all non-alphanumerics in a string.

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

**Matching Zero or More with the Star**

* means *“match zero or more”*

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

 + (or plus) means *“match one or more.”*
 
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
