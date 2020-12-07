## TABLE OF CONTENTS
1. [Built in DS](#built-in)
    1. [List](#list)
    2. [Dictionary](#dict)
    3. [Set](#set)

### <a name="built-in"/>
### Built-in DS

### <a name="list"/>
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
### <a name="dict"/>
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

### <a name="set"/>
### Sets
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
