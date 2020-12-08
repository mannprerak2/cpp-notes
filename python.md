## TABLE OF CONTENTS
1. [Built in DS](#built-in)
    1. [List](#list)
    2. [Dictionary](#dict)
    3. [Set](#set)
2. [OOP - Object Oriented Programming](#oop)
3. [Language tricks](#lang)

> [W3School Python Tutorial](https://www.w3schools.com/python/)

### <a name="built-in"/>
### Built-in DS

#### <a name="list"/>
#### List
```python
# Creating
l = []  # create empty list
l = [1, 2, 3, 'example', 3.132]  # creating list with data

# Adding
l.append(1)  # Append to end of list
l.insert(1, 'hello')  # Insert at index 1.
l.extend([234, 'more_example'])  # Extends a list.

# Access
l[3]  # access index 3 element
l[0:2]  # access elements from 0 to 1 and exclude 2
l[::-1]  # access elements in reverse

# Remvoving
a = l.pop()  # Pops last element.
l.pop(0)  # pops first element.
l.remove('example')  # remove by value
l.clear()  # clears list

# Other
l.sort()  # In-place sorting
l2 = sorted(l, reverse=True)  # returns sorted list

l = [2, 6, 1]
def keyFunc(i):
    return -i # Higher value is assigned lower values.
# The values are sorted acording to key in ascending order.
l.sort(key=keyFunc) # l = [6,2,1]
```
#### <a name="dict"/>
#### Dictionary

```python
# Creating
my_dict = {} #empty dictionary
print(my_dict)
my_dict = {1: 'Python', 2: 'Java'} #dictionary with elements
print(my_dict)

# Adding
my_dict = {'First': 'Python', 'Second': 'Java'}
print(my_dict)
my_dict['Second'] = 'C++' #changing element
print(my_dict)
my_dict['Third'] = 'Ruby' #adding key-value pair
print(my_dict)

# Removing
my_dict = {'First': 'Python', 'Second': 'Java', 'Third': 'Ruby'}
a = my_dict.pop('Third') #pop element
print('Value:', a)
print('Dictionary:', my_dict)
b = my_dict.popitem() #pop the key-value pair
print('Key, value pair:', b)
print('Dictionary', my_dict)
my_dict.clear() #empty dictionary
print('n', my_dict)

# Access
my_dict = {'First': 'Python', 'Second': 'Java'}
print(my_dict['First']) #access elements using keys
print(my_dict.get('Second'))

# Other
my_dict = {'First': 'Python', 'Second': 'Java', 'Third': 'Ruby'}
print(my_dict.keys()) #get keys
print(my_dict.values()) #get values
print(my_dict.items()) #get key-value pairs

# Acces first and last added element
my_dict.items()[0]
my_dict.items()[-1]
```

#### <a name="set"/>
#### Sets
```python
# Creating
my_set = set()
my_set = {1, 2, 3, 4, 5, 5, 5} #create set

# Adding
my_set = {1, 2, 3}
my_set.add(4) #add element to set

# Sets
my_set = {1, 2, 3, 4}
my_set_2 = {3, 4, 5, 6}
print(my_set.union(my_set_2), '----------', my_set | my_set_2)
print(my_set.intersection(my_set_2), '----------', my_set & my_set_2)
print(my_set.difference(my_set_2), '----------', my_set - my_set_2)
print(my_set.symmetric_difference(my_set_2), '----------', my_set ^ my_set_2)
my_set.clear()
```

### <a name="oop"/>
### OOP - Object oriented Programming

```python
class Person:
  def __init__(self, name, age): # Constructor
    self.name = name
    self.age = age

  def myfunc(self): # First argument is always instance of this class
    print("Hello my name is " + self.name)

p1 = Person("John", 36)
p1.myfunc()

del p1.age # Object properties can be deleted
del p1 # Objects can be deleted


class Student(Person): # Student is subclass of Person
  def __init__(self, fname, lname): # __init__ is no longer inherited as its defined
    Person.__init__(self, fname, lname) # Can do this though.
    # Or do this
    super().__init__(fname, lname)

class Assistant(Person, Employee): # Multiple inheritence
  position = 0 # This is a static/class variable and not an instance variable
  @staticmethod
  def askTime(): # This is now a static method
    return "Don't know"
```

### <a name="lang"/>
### Language Tricks

Lambdas (small anonymouse functions)
```python
def myfunc(n):
  return lambda a : a * n

mydoubler = myfunc(2)

print(mydoubler(11))
```

List Comprehension

Syntax - `newlist = [expression for item in iterable if condition == True]`

```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]
# newlist will only have names with 'a' in it
```

String formatting
```python
txt = "The price is {} dollars"
print(txt.format(price))

myorder = "I want {0} pieces of item number {1} for {2:.2f} dollars."
print(myorder.format(quantity, itemno, price))

myorder = "I have a {carname}, it is a {model}."
print(myorder.format(carname = "Ford", model = "Mustang"))
```

Exceptions
```python
if x < 0:
  raise Exception("Sorry, no numbers below zero")

try:
  f = open("demofile.txt")
  f.write("Lorum Ipsum")
except: # runs on exception
  print("Something went wrong when writing to the file")
else: # Runs only if no errors
  print("No errors")
finally: # Runs no matter what
  f.close()
```

Regexp
```python
import re

import re

print(re.split('y+','abyyyyyyss'))
print(re.search('y','abyss') is not None) # Returns match object
print(re.match('y', 'abyss')) # Matches from start (hence returns None)
print(re.match('a', 'abyss')) # Matches from start
print(re.fullmatch('.*','abyss')) # Matches full string

lis = re.split('y','abyss') # splits acc to pattern

```
