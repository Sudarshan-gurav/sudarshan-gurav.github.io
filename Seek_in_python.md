# seek in python:

**Simple Demonstartion About seek**

E.g:

'''
ABC

EFG

HIJ

KLM

NOP

'''
```python

f = open('test.txt', 'r')
cur_pos = f.tell()
print('current opsition  '+str(cur_pos))  # 0


# using readline() read line by line file.
line = f.readline()
print('current line'+str(line))     # ABC\n
 

# using read() read whole file.
line = f.read()
print('current line \n'+str(line))


cur_pos = f.tell()
print('current opsition  '+str(cur_pos)) # 4


line = f.readline()
print('current line'+str(line))   # EFG\n

cur_pos = f.tell()
print('current opsition  '+str(cur_pos)) # 8

# we will learn seek

#1st parm = starting position of file.
#2nd parm = default 0 and we can set also 1,2 .

print('seek')
f.seek (0,2)
cur_pos = f.tell()

print('current AFTER SEEK opsition file '+str(cur_pos)) #  0


line = f.read()
print(str(line))

```python







































