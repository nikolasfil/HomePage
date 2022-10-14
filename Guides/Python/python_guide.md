Python - Simple Guide/Tutorial 

Competitive Programming SG 2022-2023

This is a very short and simple python tutorial, just the very basics to be able to follow in the meetings.

It follows the turotial on python of Bro Code:
https://www.youtube.com/watch?v=XKHEtdqhLK8

Of course this is an introductory documentation.
For more information, it is best to visit the python documentation.


Installing Python : https://www.python.org/downloads/

Installing editors : 
    VSCode : https://code.visualstudio.com/docs/python/python-tutorial
    Pycharm : https://www.jetbrains.com/help/pycharm/installation-guide.html
    juypyter-notebook : https://jupyter.org/install
    


Let's start with something simple, as variables

A variable is a container for a value. Behaves as the value that it contains. We can assign various types to variables



```python
first_name = 'Milo'
last_name = 'Thatch'
full_name = first_name + ' ' + last_name

print('Hello '+full_name)
print(type(full_name))


```


```python
age = 21 
age = age + 1 
print(age)
age+=1
print(type(age))
print('Your age is :'+str(age))

```

Float = Floating point number (decimal number) 

A number that includes a decimal portion 


```python
height = 180.4 
print(height)
print(type(height))
print('Your height is '+str(height))
```

Boolean 

A variable that can only store True or False 



```python
human = True 
different = False
print(human)
print(type(human))
#useful in if statements
print('Human: '+str(human))

```


Multiple assignment 

It asllows us to assign multiple variables at the same time in one line of code 


```python
name = 'Milo'
age = 21 
attractive = True 
print(name, age, attractive)

#or in multiple assignment we can do it in one line :

name, age, attractive = 'Ross', 31, True
print(name, age, attractive)
```


```python
#another example 
Ross=Chandler=Joey = 30 
print(Ross, Chandler, Joey)
```


String methods 

len(): Returns the length of thr string 

variable.find(string): 
Returns the first occurence of string in the variable(must also be string )
It always starts counting from zero(0). 

variable.capitalize()
Capitalizes the first letter of the variable string.

variable.upper()
Changes all letters to capitals

variable.lower()
Changes all letters to lower 

variable.isdigit()
Returns true if the variable string consists of digits

variable.isalpha()
Returns true if the variable string consists only of letters

variable.count(string)
Returns the number of string occurences in the variable

variable.replace(from, to)
Returns the variable but replaces the from part with to part 


Mutliplication between string s and integer i will return a new string that consists of i times s . 



```python
name = 'first Name'

#legnth of string
print(len(name))

#find method 
print(name.find('i'))

#capitalize
print(name.capitalize())

#upper
print(name.upper())

#lower
print(name.lower())

print(name.isdigit())
print('01'.isdigit())

print(name.isalpha())
print('01'.isalpha())


#multiple printing feature
print(name*10)

```


Typecasting

Convert the data type of a value to another type 



```python
x = 1    #int
y = 2.1  #float
z = "3"  #str


print(int(y)) # not a permamenet change 

new_y = int(y)

print(z*3)    # returns str
print(int(z)*3) # returns int 

new_x ,new_z= float(x), float(z)
print(new_x, y, new_z)


```

User Input 

input(message) 
It will print message and expect input
It will save the input as a str format. For any other format you have to typecast it 


```python
name=input('What is your name?')
print('Hello '+ name)

age = int(input('What is your age?'))
print('You are '+str(age)+' years old')

```

Useful functions related to numbers 

import math 

math is a library in python that has very useful functions
With import we can use the library like math.function() 

math.ceil(number):
rounds up 

math.floor(number):
round down

abs(number):
returns the absolute value of the number

pow(number, power)
Returns the number to the power of power (number ^ power)

math.sqrt(number):
returns the square root of a number

max(numbers *)
returns the max value from the values given 



```python
import math

pi = 3.1415926
print(round(pi))

print(math.ceil(pi))

print(math.floor(pi))

print(abs(pi))

print(pow(pi,2))

print(math.sqrt(81))

x = 0
y = 2 
z = 1 
print(max(x,y,z))

```

String Slicing 
create a substring by extracting elements from another string 

indexing[] is using the brackets [] , [start:stop:step] 

start 0 can be omitted.
stop is up until the number we want, so 0:3 displays 0,1,2 letters

the last (length of word -1 ) can also be omitted
len(word)-1 and -1 is the same
You can go on negative numbers, and it will just be counting normally from the end

slice() is a function




```python
name = 'Full Name'
print(name[1])

first_name = name[:4]
last_name = name[5:]
print(name[5:len(name)]) # yields the same result

#every two letters print 
print(name[::2])

#reversing
print(name[::-1])


```

Slicing Function

creates a slice object, that takes three variables (start, stop , step ) 
step is on default 1 


```python
website = 'http://google.com'
slice_obj = slice(7,-1)
print(slice)
```

If statement 

A block of code that will execute only if it's condition is true

else statement stands for all the other cases that if checks.

elif checks a different statement inside the if statement structure

if a condition is fullfield then the rest of the elifs and else are omitted.


```python
age = int(input("Age: "))
if age >= 18: 
    print('adult')
elif age == 21:
    print('you are an adult and have start drinking')
elif age <0:
    print('You are are not born yet ')
else:
    print('you are a child')
```

Logical operators (and, or, not) 

Used to check if two or more conditional statement are true 

and : needs all the statements to be true in order to return true 
or: needs at least one statement to be true in order to return true
not: returns the opposite boolean value 



```python
print(True or False)
print(True and True)

temp = int(input('temperature: '))
if temp >=0 and temp <= 30 : 
    print('The temperature is good \n You can go outside')
elif temp<0 or temp > 30 : 
    print('the temperature is not good today\n stay inside')

# same results yields : 

if not (temp >=0 and temp <= 30) : 
    print('the temperature is not good today\n stay inside')
elif not( temp<0 or temp > 30 ): 
        print('The temperature is good \n You can go outside')

```

While Loop 

A statement that will execute it's block of code, as long as it's condition remain true 

example of an infinite loop : 

while 1==1:
    print('stuck in an infinite loop')

to get out of the infinite loop ctr+C mostly works as a keyboard interrupt for the program 



```python
name = '' 

while len(name) == 0 : 
    name = input('enter your name: ')

#same result : 

while not name:
    name = input('enter your name:' )
```

For loop : 

A statement that will execute it's block of code a limited amount of times 

range(start, stop, step)



```python
for i in range(10):
    print(i)

for i in range(50,100):
    print(i)

for i in 'this is a string':
    print(i)
        
```


Nested loops 

The inner loop will finish all of it's iterations before finishing the iteration of the outer loop 


```python
row = ''
for i in range(10):
    for j in range(10):
       row+= '#'
    print(row)
    
# or same result

for i in range(10):
    for j in range(10):
        print('#', end = '')
    print()
    
    
```

Loop Control statements : 

Used to change a loops execution from it's normal sequence 

break : used to terminate the loop entirely 
continye : skips to the next iteration of the loop 
pass : does nothing acts as a placeholder 



```python
while True:
    name = input('Name: ')
    if name !='':
        break

phonenumber= '123-4567-890'
for i in phonenumber:
    if i =='-':
        continue
    print(i,end = '')


for i in range(1,21):
    if i == 13:
        pass 
    else:
        print(i)
    
```

Lists: 

used to store multiple items in a single variable 

You use indexing for access to individual elements
[Start:stop:step] is also usable 
Unlike string, we can change individual elements of the list 


```python
food = ['pizza', 'spaghetti','hotdog']

print(food)

#accessing elements inside the list: 

print(food[1]) #second element

food[1]='fruits'
print(food)
```

Useful functions 

list.append(item)
Adds the item to the end of the list

list.remove(item)
removes the item specified 

list.pop()
removes the last item

list.insert(position, item)
adds the item to the position specified

list.sort()
sorts the list. Look also sorted(list)

list.clear()
Clears the list




```python
food = ['pizza', 'spaghetti','hotdog']
food.append('ice cream')
print(food)

food.remove('pizza')
print(food)

food.pop()
print(food)

food.insert(1,'pizza')
print(food)

#print(sorted(food))
food.sort()
print(food)

for x in food:
    print(x)
```

multidimentional lists: 

lists with elements that are lists 


```python
drinks = ['cofee','soda','tea']
dinner = ['pizza','hamburger','hotdog']

food = [drinks, dinner]

#accessing the list
print(food[0][1])
#accessing outer -> inner 

```

Tuple : 

Collection which is ordered and unchangeable, used to group together related data

Same as a list , but once created cannot be changed.


```python
student = ('Milo',21,'male')
print(student.count('male'))
print(student.index(21))
for x in student :
    print(x)
if 'Milo' in student:
    print('Milo is here ')

```

Set

Collections which is unordered, unidexed
No duplicate values are allowed. 
uses {} to initiate an empty set

Can be faster than a list to see if something is within a list 


```python
objects = {}
objects = {'headphones','laptop','phone'}

for x in objects : 
    print(x)

#It might not be the same order that was inserted 
print(objects)

new_objects = {'plates','book','book','phone','phone','phone','phone'}
print(new_objects)

objects.add('charger')
objects.remove('headphones')
print(objects)

#adding one set to another 
new_objects.update(objects)
print(new_objects)

new_objects = {'keys','napkin','earbuds'}
objects = {'laptop','headphones','phone'}
# Joining sets
common_objects=new_objects.union(objects)
print(common_objects)

objects = {'keys','hat','rings','phone'}
# Compare differences
print(common_objects.difference(objects))

# Compare similarities 
print(common_objects.intersection(objects))

```


Dictionaries 

A changeable, unordered collection of unique key: value pairs.
It uses hashing, that's why they are so fast.

dictionary\[key\]=value



```python
am = {'Bob':1022,'Martha':1032,'Stuart':1055}

print(am['Bob'])

# Setting/Changing values of specific keys
am['Bob'] = 1021
print(am['Bob'])

# The key has to exist in the dictionary 
print(am.get('Bob'))
# iF the key doesn't exist in the dictionary, returns None
print(am.get('Sully'))


for key in am.keys():
    print(key)

for value in am.values():
    print(value)
    
for items in am.items():
#     items returns a tuple (key, value)
    print(items)
    
# removing 
am.pop('Bob')
# clear
am.clear()
```


Index Operator \[\]

Gives access to a sequence's element (str, list, tuples)




```python

name = 'milo Thatch'
if name[0].islower():
    name = name.capitalize()

first_name = name[0:4]
last_name = name[5:].capitalize()
print(first_name,last_name)
```


```python
# we can access negative indexes, counting from the end -1 .. 
last_character = 'this is a str'[-1]
print(last_character)
```


Functions

A block of code that is executed only when it is called (invoked)

Needs the def keyword, a name for the function followed by parenthesis() and inside the parenthesis could be some arguments(parameters) that the function needs 
Arguments can be whatever data types we want.

The commands inside the function are indented , like the if-else,for loops, while loops commands

The arguments can have a default value as well. With default values, functions can be called without any parameters given



```python

def hello():
    print('hello')

hello()    
    
def greetings(name):
    print('Greetings '+str(name))

greetings(input())

def greetings(name='Unknown'):
    print("Greetings "+name)
greetings()

def typing(name,age,hobbies):
    print(type(name),type(age),type(hobbies))

typing('Milo',23,['Linguistics','Exploration','Boiler Master'])
```


Return Statement 

Functions send python values/objects back to the caller 
These values/objects are known as the function's return value 

You can either print them directly to the console, or store them in variables



```python
def adder(num1,num2):
    return num1+num2

print(adder(3,8))

variable = adder(12,3)

```


Keyword arguments

Arguments preceded by and identifier when we pass them to a function.
The order of the arguments doesn't matter, unlike positional Argumnets Python knwons the names of the arguments that our function receives 



```python

def typing(name,age,hobbies):
    print(type(name),type(age),type(hobbies))

typing('Milo',23,['Linguistics','Exploration','Boiler Master'])

typing(age=23,hobbies=['Dead Languages'],name='Milo')
# No matter that the order has changed, 
# it still displays it with the order we have coded it to  

```


Nested Function calls 

function calls inside other function calls 
Innermost function calls are resolved first 
Returned Value is used as argument for the next outer function 




```python
num = input('Whole Positive Number')
num = float(num)
num = abs(num)
num = round(num)
print(num)

print(round(abs(float(input('Whole Positive Number')))))

```


Scope 
The region that a variable is recognized 
A variable is only available from inside the region it is created 
A global and locally scoped versions of a variable can be created 

Python uses the LEGB rule 
L = Local 
E = Enclosing 
G = Global 
B = Built-in 



```python

def display_name():
    name = 'Milo' # local
    print(name)

# print(name) is going to raise error
name = 'Thatcher'
print(name)

```


```python
name = 'Milo' # global
def display_name():
    print(name)
    name = 'Thatch' #local
    print(name)
print(name)
```


*args 

Parameter that will pack all arguments into a tuple 

args can be named whatever you want, the * before is that does all the job


```python

def add(*nums):
    s = 0 
    for i in nums:
        s+=i
    return s 

print(add(0,1,2,3,4,5,6,7,8))
```


\**kwargs
Packs all arhuments into a dictionary, can accept a varying amount of keyword arguments 




```python

def hello(**name):
    print('Hello '+name['first'] +' ' + name['middle'] +' ' + name['last'])

hello(first='Milo',middle='G.', last='Thatcher')

def hello(**names):
    print('Hello',end=' ')
    for key,value in names.items():
        print(value,end=' ')
hello(first='Milo',middle='G.', last='Thatcher')

```


Format method 

str.format() 
A method available for strings , 
It is an optional method that gives users more control when displaying output

{} is a place holder 
In format it is ordered 

{number} will place the index_number item from the format 


'{Argument}'.format(argument=value)



```python

animal = 'cow'
item = 'moon'

print('The {} jumped over the {}'.format(animal,item))
print('The {1} jumped over the {0}'.format(animal,item))

print('The {animal} jumped over the {location}'.format(location='moon',animal='cow'))

```

Adding some padding 
{:after} 


```python
print('{:10} see ?'.format('Now You'))

# left align
print('{:<10} see ?'.format('Now You'))

# right align
print('{:>10} see ?'.format('Now You'))

# Center align
print('{:^10} see ?'.format('Now You'))

print('{name:^10}'.format(name = 'Milo Thatch'))
```

formating numbers 



```python
number = 3.1415926535
print('The number pi is {:.3f}'.format(number))

number = 5
# binary representation
print('The binary is {:b}'.format(number))
print('The hex is {:X}'.format(number))
print('The oct is {:o}'.format(number))
print('The scientific number is {:E}'.format(number))

```


Power strings 



```python

```

Random Numbers


```python

```


Exception : 

Events detected during execution that interrupts the flow of a program

We use a try block to handle code that can be dangerous 



```python
try:
    n = int(input('Enter A number:'))
    d = int(input('Enter A number'))
    result = n /d
except ZeroDivisionError:
#     We can look out for specific errors
    print("Can't divide by zero")
except ValueError:
    print('Enter only numbers')
except Exception as e : 
#     or we can simply see the error without disrupting the 
#     flow of our program
#     e is the exception that was raised 
    print(e)
    
else:
#     this runs if no exceptions are occured
    print(result)
finally:
#     runs at the end of try except regardless of 
#     the rest
    print('This was division')
    
```





```python

```
