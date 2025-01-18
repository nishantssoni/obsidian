

Things to learn : Scipy, Pylab, Sklearn, Patool

# Module 1: Fundamental of programming.

## Chapter 1: How to utilise AAC

---

- Some tips for learning from this course:
- Used breadth first technique: learn upper concept then go deeper.
- Used feynman technique for learning concepts.


**

## Chapter 2 : Python for Data Science: Introduction

---

### Python, Anaconda and relevant packages installations:

- See videos of Corey schfer in anaconda.
    
- Install required packages and learn about virtual env variables.
    
- conda config --set auto_activate_base False: this code is used to off the default launch of root environment variable
    
- source ~/anaconda3/bin/activate root anaconda-navigator: use this command to or conda activate to activate the base environment after that use what you want.
    
- For tensorflow :: pip3 install --upgrade tensorflow
    
- [https://www.youtube.com/watch?v=hbUJ6nd-9lA](https://www.youtube.com/watch?v=hbUJ6nd-9lA) 
    
- [https://repo.continuum.io/archive/](https://repo.continuum.io/archive/) 
    

  
  

### Why learn Python?

- Python is very simple to pick up.
    
- Packages useful for ML are available in Python.
    
- Jupyter Notebooks for interactive programming.
    
- Extensively used in the industry.
    
- Python is a much more general purpose programming language.
    

  

### Keywords and Identifiers:

- Keywords are the reserved words in python.
    
- We can’t use a keyword as variable name, function name or any other identifier.
    
- Keywords are case sensitive.
    
- Keywords Example: False, None, True, class, if, else, return, def, try, while, for, etc.
    
- Total number of keywords: 35.
    
- Names given to entities like class, functions and variables are called identifiers.
    
- It can be a combination of letters, digits and underscores, can not start with a digit.
    
- Keywords cannot be used as identifiers, special characters cannot be used.
    
- Python has straight forward Error indications.
    
- Following code displays all the keywords in python
    

  
  
  
  

|   |   |
|---|---|
|code|output|
|Import keyword<br><br>print(keyword.kwlist)<br><br>print(“\|nTotal no of keyword is”,len(keyword.kwlist)|['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']<br><br>Total no of keyword is 35|

  
  

### Comments, Indentation, and Statements:

- Start a line with a # for single line comment or use triple quotes, “””   “””  for multiple line comment.
    
- Indentations are used (4 spaces preferred) to make blocks of code.
    
- Rather than writing code in a single line try to write in multiple lines (can use \ in the end of line or put everything in parentheses if you don’t want to put \ ) to make code readable.
    
- The written instructions are called statements(single line statement and multiple line statement.
    
- Put a multiple statement in a single line using semicolon ‘ ; ‘. e.g: a=12;b=13;print(a+b).
    

  

### Variables and data types in python:

- Variable is a location in memory used to store some data.
    
- Variable declaration is not needed.
    
- a, b = 10, ‘Hi’  :: multiple assignment.
    
- a = b = c = 22
    
- id(a) prints address or memory location of a data type.
    
- If two variables have the same value then both have the same address and if you change one of them the address will be changed because the python compiler does this to save space.
    
- Everything in python is an object.
    
- We can use type() function to use which class a variable or a value belongs to and isinstance( object , class ) :: return boolean value ⇒ to check the object if from a particular class or not.
    
- Number: Integers, float and complex( a+bj is a complex number e.g: 2+3j).
    
- Boolean: True and False
    
- Strings: Sequence of Unicode characters, defined with quotes, indexable, slicable.
    
- List: An ordered sequence of items, like an array, can have , defined with square brackets; Lists are mutable(you can modify).
    
- Tuple: Defined with parenthesis, can have multiple data type elements, tuple is immutable, can be indexable
    
- Set: Defined with Curly braces, Set is an unordered collection of unique items; behaves as a set in mathematics does not support indexing.
    
- Dictionary: an unordered collection of key-value pairs, defined with curly braces and a colon, value accessible with key
    
- Data types can be converted provided the value is valid in both data types;
    
- List(‘Hello’) = [‘H’,’e’,’l’,’l’,’o’], float(), int() etc are used for data conversion
    
- Str[5: ] ⇒ it tells thant print from index 5 to last.
    

  

### Standard Input and Output:

- print(‘ {a} {b}’.format(a = 1, b = 2))
    
- print( f’hi my name is {name} and my roll no is {roll}’)
    
- Input:
    
- input()
    

  

### Operators:

- Operators are special symbols in python that allow arithmetic or logic computation.
    
- 2 + 3 : + is an operator and 2, 3 are operands
    
- Types: Arithmetic, Comparison, Logical, Bitwise, Assignment, Special
    
- Arithmetic: +, -, *, /, %, //, ** (addition, subtraction, multiplication, division, modulo, division, floor division, exponent)
    
- -15//2 = -8 and 15//2 = 7   {floor division means closest integer from the value and less than the value.
    
- Comparison: <, >, !=, ==, >=, <=
    
- Logical: and, or, not
    
- Bitwise:
    
- a= 10, b = 4:
    

a & b: 1010 & 0100: 0000 (and) = 0

a | b: 1110 = 14

or: |, not: -, xor: ~, right shift: >>, leftshift: <<

a>>b:

- Assignment operator:  =, +=, -=, *=, /=, %=, //=, **=, &=, |=
    
- a += 10: a = a + 10
    
- Identity operators: is, is not ⇒ they are used to check if two variables or values are located in the same part of memory ( it doesn't work with complex data types like list ,tuple etc).
    
- Membership operators: In, not in ⇒ it is used to check whether a value is found in a sequence variable like (list, tuple, string etc).
    
- Membership operators like in and not is used in dictionaries to find keys not the values of the data type.
    

  
  

### Control flow: If...else

- If test expression:
    

   statement(s)

- Everything in python is taken as true except 0, none and false.
    
- You can make a nested if else statement or you can use elif for multiple expression checking.
    

  
  

### Control flow: while loop:

- While loop: block of code runs until a test expression is true.
    
- while test expression:
    

    Body of a while loop

- while tents expression:   //here when the loop fails then the else part runs.
    

    Body of a while loop

else:

    Else part of the whole loop.

  

### Control flow: for loop:

- for i in range( starting,end,steps ) // i is a variable
    

    For loop body

- You can also add else after for loop
    

  

### Control flow: break and continue:

- Break is used to jump out of a particular block of code.
    
- Continue is used when we want the current loop to be skipped in the next loop.
    

  
**


**

---

## Chapter 3 : Python for Data Science: Data Structure

---

  

### Lists:

- Data Structures: collection of data elements
    
- List: Sequence data structures, these are indexable, mutable, defined by square brackets and elements are comma separated.
    
- len(list) //len of a list
    
- append(element) //add element in last index
    
- insert(index, element) //and element in particular index
    
- remove(element) //removes first occurrence only
    
- [‘one’, ’two’].append([‘one’, ’two’]) = [‘one’, ’two’, [‘one’, ’two’]]
    
- [‘one’, ’two’].extend([‘one’, ’two’]) = [‘one’, ’two’, ‘one’, ’two’]
    
- del list[1] //it delete the given index element of list
    
- pop(index) //it delete the given index and return deleted item
    
- list reverse: list.reverse() //reverse the original list
    
- sorted(list), list.sort() //sort the original list
    
- Keywords ‘in’ and ‘not in (combine ‘in’ in ‘not keywords’)’ are used to test if the item is on the list or not and return boolean value. E.g : 3 in list : true 3 not in list :false
    
- sorted(list) //it sort the list and return it without affecting original one
    
- sorted(list,reverse=True) //it reverse sorted and same as above only return
    
- lst = [1, 2, 3, 4, 5]; abc = lst; abc.append(6); print(lst)  [1, 2, 3, 4, 5, 6] ⇒ lst and abc are pointers.
    
- string.split(‘ ‘) //split the string by given parameter and return a list of split
    
- The default split parameter is space so if you put split() then it splits where space or tab is otherwise you can change the parameter.
    
- lst[slice_index_start: slice_index_end]    //slice the given list from index start to the one below the index end and return without affecting the original list.
    
- List[:] //print start to end
    
- List[start index:end index:steps] //steps indicate how many steps to leave
    
- new_list = lst1 + lst2 //extend and merge lst1 the lst2 and fetch in new_list
    
- lst.count(element) //it tells the number of times the element occurs.
    
- for a in list:
    

    print(a) //print all the element in a

- List comprehensions: it is a conscious way to writing a list when each element is the result of some operation in titratable way :
    

|   |   |   |
|---|---|---|
|Sn. no|code|output|
|1|square = [i**2 for i in range(10)]<br><br>print(square)|[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]|
|2|square = [(i%2==0) for i in range(10)]<br><br>print(square)|[True, False, True, False, True, False, True, False, True, False]|
|3|square =  [i**2 for i in range(10) if i%2 !=0]<br><br>print(square)|[1, 9, 25, 49, 81]|
|4|lst = [1,2,3,4,5,6,7]<br><br>new_lst = [i*2 for i in lst if i>3]<br><br>print(new_lst)|[8, 10, 12, 14]|
|5|lst = [(i,i**2,i**3) for i in range(5)]<br><br>print(lst)|[(0, 0, 0), (1, 1, 1), (2, 4, 8), (3, 9, 27), (4, 16, 64)]<br><br>//it is tuple you can also make list inside a list|

  

- Below the example of List comprehensions both have same output:
    

|   |   |
|---|---|
|code|output|
|#transpose without list comprehension<br><br>transposed =[]<br><br>for i in range(4):<br><br>    lst = []<br><br>    for row in matrix:<br><br>        lst.append(row[i])<br><br>    transposed.append(lst)<br><br>print(transposed)|[[1, 5, 9], [2, 6, 10], [3, 7, 11]]|
|#transpose using list comprehension<br><br>transposed = [[row[i] for row in matrix] for i in range(len(matrix))]<br><br>print(transposed)|[[1, 5, 9], [2, 6, 10], [3, 7, 11]]|

  
  
  
  

### Tuples part 1:

- A tuple is similar to a list.
    
- Tuple is immutable, its elements cannot be altered.
    
- a = (‘satish’)
    

type(a) //type string

- A = (‘satish’,)
    

type(a) //type tuple because if you put only one element then you have to put a comma in last otherwise python thinks it is particular that element.

- You can use tuple the same as list but only you can’t change the value of tuple.
    
- Slicing is also the same as list e.g tup[1:4:2].
    
- If a element inside a tuple is mutable then you can change that e.g:
    

t = (1,2,3,4,[“nishant’,”sony”],5)

t[4][1] =”soni” //valid you can do that

- You can concatenate or add a tuple:
    

t = (1,2,3)

t2 = (4,5,6)

t += t2

print(t) //(1,2,3,4,5,6)

- Repeat the element in tuple in the given number times using * operator:
    

t = ((“nishant”,)*4)

print(t)

  

### Tuples part 2:

- Deletion: whole tuple will be deleted.
    

del t //delete whole tupel

-  Tuple.count()
    
- tuple.index(element)(return index of first occurrence)
    
- element in tuple
    
- element not in tuple
    
- len(tuple)
    
- sorted(tuple)
    
- min(tuple)
    
- max(tuple)
    
- sum(tuple)
    

  

### Sets:

- Sets are an unordered collection of unique items(no duplicates), Mutable, non-indexable.
    
- Sets do not allow duplicates they store only one instance of a element e.g 
    

s={1,2,3,4,2}

print(s) //{1,2,3,4}

- s[2] //type error because you can’t index a set.
    
- set.add(element) //add element to a set
    
- set.update(list or tuple or set) //add to set or you can also use comma with that
    
- s.discard(element)(does not generate error when element is not present)  or set.remove(element) //remove particular element set from the list.
    
- s.pop() //remove one element random at a time.
    
- s.clear() //remove all element in a set clear() method
    
- Set1 | Set2: Union; Set1.union(Set2)
    
- Set1 & Set2, Set1.intersection(Set2)
    
- Set1 – Set2, Set1.difference(Set2)
    
- Set1^Set2, Set1.symmetric_difference(Set2)): Union - Intersection
    
- set1.issubset(set2) //set1 is subset of set2 or not return bool
    
- Frozenset: immutable sets: Set1 = frozenset([1,2,3,4])
    

### Dictionary or a hash table:

- An unordered collection(cannot index) of key value pairs;
    
- My_dict = {1:”nishant”,2:”soni”}
    
- my_dict = dict( [(‘a’,234),(‘b’,97438),(‘c’,4987)] ) //we can use dict to create a dictionary from a list of tuples.
    
- O(1) for time complexity for search tasks;
    
- .get(key) //if key is not present then it give none but in direct access by square brackets if the key is not present then it give key error
    
- For adding new key and value assign new key like array e.g
    

My_dict = {‘name’:’nishant’,”last”:”soni”}

My_dict[“address”] = “ranchi”

- Dictionary is mutable;
    
- dict.pop(key) //remove element and return the remove element
    
- dict.popitem() //remove any element random
    
- del dict[2] //remove element of key name 2
    
- dict.clear() //remove dict
    
- dict.fromkeys(list, values) //This method creates a new dictionary where the keys are taken from the given list, and all the values are set to a specified value.
    

Subject = {}.fromkeys([‘maths’,’eng’,’bio’],0)

⇒ subject = {‘maths’:0,’eng’:0,’bio’:0}

  

- dict.items() //return dict in format of list of tuples
    
- .keys() //return keys in list
    
- .values() //return values in list
    
- .copy()
    
- for pair in d.items(): print(pair)
    

#### Dictionary Comprehension:

    mydict = {k:(k**5) for k in range (10)}

    print(mydict)

 {0: 0, 1: 1, 2: 32, 3: 243, 4: 1024, 5: 3125, 6: 7776, 7: 16807, 8: 32768, 9: 59049}

  

    new_mydict = {k:v for k,v in mydict.items() if v%2==0}

    print(new_mydict)

              {0: 0, 2: 32, 4: 1024, 6: 7776, 8: 32768}

  

### Strings:

- Sequence of characters:(Unicode (default) or ASCII)
    
- The conversion of character to a number is called encoding. S = “kl” or = str(1)
    
- Access characters and use the function  of a string as a list.
    
- Strings are immutable;
    
- Operations: str1+str2; for i in string: ______;
    
- lower(), upper(), join()(opposite of split), split(), find(), replace()
    
- “Bad Morning”.replace(“Bad”, “Good”)  //it return the replace word Good morning
    

  
  

#To check string is palindrome or not

my_str = 'mADam'

​

#convert string in lower

my_str = my_str.lower()

​

#reverse string

revStr = reversed(my_str)

​

#check the string is equal to it reversed and print palindrome or not

if list(revStr) == list(my_str):#because revStr == my_str have different memory location

    print("Given string is palindrome")

else:

    print("Given string is not palindrome")

Output:  Given string is palindrome

  
  

#Python program to sort word in alphabetical order

my_str = "python program to sort word in alphabetical order"

​

#breaking down the string into list of word

wrds = my_str.split()

​

#sort the list

wrds.sort()

​

#printed sorted words

for i in wrds:

    print(i)

Output: alphabetic  In  Order  Program  Python  Sort  to

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

---

## Chapter 4 : Python for Data Science: Functions

---

### Introduction

- a group of related statements that perform a specific task.
    
- Converts a program into smaller chunk which makes management easy
    

def fun(x):

    #Doc strings is written to explain the working of the function (function.__doc__)

"""doc string"""

    print("i am the body of function")

    return x

  

- Doc string is optional but writing doc string is a good programming practice.
    
- Accessing doc string is funtion_name.__doc__
    
- Return statement is optional when we don't return anything. Python returns None object.
    
- Scope of the variable is the portion of the code where the variable is recognized and Lifetime of a variable is the period throughout which the variable exists in memory
    
- Variables inside a function are local variables which are destroyed once the function finishes execution.
    
- Global variables are not destroyed unless deleted;
    
- Program to print highest common factor (HCF):
    

  

def computeHCF(a,b):

   """computing HCF of two numbers"""

   smaller = b if a>b else a #concise way of if else

   hcf = 1

   for i in range(1,smaller+1):

       if (a % i == 0) and (b % i == 0):

           hcf = i

   return hcf

num1=98

num2=78

print('HCF of {0} and {1} is {2}'.format(num1,num2,computeHCF(num1,num2)))

Output: HCF of 98 and 78 is 2

  

### Types of Functions

- Built-in Functions and User defined functions.
    
- abs() //return absolute value of a number
    
- all()
    

  

#True: if all element in an iterable are true

#False: if any element in an iterable are false

  

lst = [1,2,3,4]

print(all(lst))

output:True

  

lst = (0,1,2,3,4)  #0 is present in list

print(all(lst))

output:False

  

  

lst = ()     #empty list is always true

print(all(lst))

output:True

  

lst = [1,False,2]

print(all(lst))

output:False

  

- any()
    
- dir() //it returns a list of valid attributes of the object.
    
- divmod()
    

#divmod() take two number and return a pair(tuple) of number of their (quotient, remainder)

​

print(divmod(16,3))

output:(5, 1)

  

- enumerate(iterable,start=0) //return value in the pair of (index,value)
    

  

nums = [10,20,30,40]

for index,value in enumerate(nums):

   print("index {0} has value {1}".format(index,value))

index 0 has value 10

index 1 has value 20

index 2 has value 30

index 3 has value 40

- filter():construct an iterator from elements of an iterable for which a function returns true.it filter the list when the function given in parameter returns true.
    

  

def find_positive_number(num):

   """it returns the positive number"""

   if num > 0:

       return num

number_list = range(-10,10) #create a list with number from -10 to 10

print(list(number_list))

​

positive_num_list = list(filter(find_positive_number,number_list))

print(positive_num_list)

[-10, -9, -8, -7, -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

[1, 2, 3, 4, 5, 6, 7, 8, 9]

  

- map(): it applies function to all the items in an input list.
    

  

numbers = [1,2,3,4,5]

​

def powerOfTwo(num):

   return num**2

​

#using map function

squares = list(map(powerOfTwo,numbers))

print(squares)

output:[1, 4, 9, 16, 25]

  

- reduce(): performing some computation on a list and returning the result. It applies a rolling computation(every element not like map() or filter() which apply in individual items you can use reduce when you want to perform in every element sequence like code below mentioned) to a sequential pair of values in a list.
    

  

#importing reduce

from functools import reduce  #python3

​

lst = [1,2,3,4,5]

def multiply(x,y):

   return x*y

​

product = reduce(multiply,lst)

print(product)

output:120

  

- isinstance(value,datatype) //return true if the value if instance of given data type
    
- enumerate(): // returns a list with an index
    
- filter(): //applies a function on a list to reduce the list
    
- map(): //applies a function on all items of a list
    
- def PowerOfTwo(num):
    
- Return num**2
    
- map(PowerOfTwo, list)
    
- reduce(): applies a computation and returns a result;
    
-   
    

### Function Arguments

- Functions need inputs which take in values through arguments;
    
- Default arguments: to give default values to a function. have default arguments at the end
    
- Keyword arguments: variable number of arguments can be given as input. Kwargs allows you to pass keyword variable length of argument to the function. You should use **kwargs if you want to handle name arguments.
    

  

def greet(**kwargs):  #kwargs is read as keyword argument

   """this function greet the person with its name and message"""

   if kwargs:

       print("Hello {0} , {1}".format(kwargs['name'],kwargs['msg']))

​

greet(name = "nishant",msg = "Good morning" )

Output: Hello nishant , Good morning

  

- Arbitrary arguments: Used when number of arguments are unknown given as input to the function.
    

  

def greet(*names):

   """this function greets all the person in the name tuple"""

   print(names)

   for name in names:

       print("hello, {0}".format(name))

greet('nishant','shekhar','soni','anurag','durgesh')

('nishant', 'shekhar', 'soni', 'anurag', 'durgesh')

hello, nishant

hello, shekhar

hello, soni

hello, anurag

hello, durgesh

  

### Recursive Functions

- Function calling inside itself
    

  

#python program to print factorial of a number using recursion

def factorial(num):

   """return factorial of a number"""

   return 1 if num == 1 else (num*factorial(num-1))

​

print(factorial(5))

Output: 120

  

### Anonymous/Lambda Functions

- Functions without name;.used along with filter and map
    

  

square = lambda x: x**2  #here we given name to lambda function

print(square(5))

Output: 25

  
  

#example: lambda function use with filter()

lst = [1,2,3,4,5,6,7]

  

#syntext: filter(function_name,iterable)

new_list = list(filter(lambda x: (x%2 == 0), lst))

print(new_list)

Output: [2, 4, 6]

  

#example: lambda function use with map()

lst = [1,2,3,4,5,6,7]

new_list = list(map(lambda x: x**2, lst))

print(new_list)

Output: [1, 4, 9, 16, 25, 36, 49]

  

#example: lambda function use with reduce()

from functools import reduce

​

lst = [1,2,3,4,5,6,7]

product_lst = reduce(lambda x, y: x*y,lst)

print(product_lst)

Output: 5040

  
  

### Modules

- Module refers to a file containing statements and definitions.Module is basically a file which contains classes and functions.
    
- A .py file containing code that is used in other programs
    
-   
    

import datetime

datetime.datetime.now()

Output: datetime.datetime(2021, 5, 6, 5, 31, 30, 808483)

  

- Import with renaming : import math as m
    
- from module_name import something : you can specifically import some function or value from the module without including the whole module.
    
- from math import * : asterisk sign means you import all the functions from the module. It is equal to importing the whole math module.
    
- You can use dir() functions to find out all the names that are defined inside a module.
    

  
  
  
  
  
  
  
  

### Packages:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdM1q-jYpP238FEGAb4Iug9e2ReYomVtL-PsWELu4ulHsz83JxPhy8IzG8kPhwQTYFzSJ9elS9BwS1w5karHoaxV7NYfnKYyW8CMh9oIInC_htU1n-tC71rh43TMtUG3e61EUaz6t41_uIeuhHhLHjUKtI?key=8Qt00RxXoDU0UfpdlgjMlA)

- Package is a kind of directory which contains modules of similar type. Or packages are a way of structuring python’s module namespace by using “dotted module names(if you put dot then you can go inside it e.g: game.sound.load)”.
    
- __init__.py needs to be present in a folder to consider the folder as a package.
    
- In __init__.py you can leave it empty but it is used to load or initialize files just like a constructor.
    
- Library is a collection of Packages.
    
- Framework is a collection of Libraries.
    
- E.g for importing something from package: import Game.Sound.play
    

  

### File Handling

- Storing data in a hard disk which is non-volatile.
    
- Because RAM is volatile it loses its memory when turned off, so we store it non-volatile to permanently store our data.
    
- Flow of file i/0 : Open, read and close
    
- File = open(‘example.txt’): Open a file in the current directory this is an inbuilt function which returns a file object also called handle, as it is used to read or modify the file accordingly.
    
- open(“name_of_file,’r’) :  reading (default)
    
- open(“name_of_file,’w’) : writing (creates a new file, if exists deletes it)
    
- open(“name_of_file,’x’) : exclusive creation if a file already exists then it shows error.
    
- open(“name_of_file,’a’): open for appending at the end of the file without truncating(deleting) the file and creating a file if it doesn't exist.
    
- open(“name_of_file,’t’): open in text mode(default)
    
- open(“name_of_file,’b’): open in binary mode
    
- open(“name_of_file,’+’): open a file for updating
    

f = open('example.txt')  #equivalent to 'r'

f = open('example.txt','r')

​

f = open('example.txt','w')

  

- The default encoding is platform dependent.in windows it is ‘cp1252’ but ‘utf-8’ in linux. So we must not rely on the default encoding or else our code will behave differently in the different platforms.Hence, when working with a file in text mode it is highly recommended to specify the encoding type.
    
- Closing a file:  File_name.close() : to make sure the data is not volatile
    
- Closing the file will free up the resources that were tied with the file and its done by using close() method.
    
- Python has a garbage collector to clean up unreferenced objects but, we must not rely on it to close the file otherwise it stores in ram when we don’t close so our data is in danger that's why we must close the file.
    
- f.close() is not entirely safe . if an exception occurs, the code exit without closing.Use safer “try finally” block: Exception handling
    

  

try:

   f = open('example.txt')

finally:

   f.close()

From the above code we can say that the file is closed even if an exception occurs in the program.

- open(‘example.txt’,encoding=’utf-8’)
    

  

#### Writing to a File

In order to write into a file we need to open it in write 'w', append 'a' or exclusive creation 'x' mode.

We need to be careful with the 'w' mode as it will overwrite into the file if it already exists. All previous data are erased.

Writing a string or sequence of bytes (for binary files) is done using write() method. This method returns the number of characters written to the file.

  

f = open("test.txt", "w")

f.write("This is a First File\n")

f.write("Contains two lines\n")

f.close()

  

This program will create a new file named 'test.txt' if it does not exist. If it does exist, it is overwritten.

  

#### Reading From a File

  

There are various methods available for this purpose. We can use the read(size) method to read in a size number of data. If the size parameter is not specified, it reads and returns up to the end of the file.

  

  

f = open("test.txt", "r")

f.read()

'This is a First File\nContains two lines\n'

f = open("test.txt", "r")

f.read(4)

'This'

f.read(10)

' is a Firs' //because cursor is in 4th position from above code.

  

We can change our current file cursor (position) using the seek() method.

Similarly, the tell() method returns our current position (in number of bytes).

  

f.tell()

14

  

f.seek(0) #bring the file cursor to initial position

print(f.read()) #read the entire file

  
  

We can read a file line-by-line using a for loop. This is both efficient and fast.

  

f.seek(0)

for line in f:

   print(line)

This is a First File

  

Contains two lines

  
  

Alternatively, we can use readline() method to read individual lines of a file. This method reads a file till the newline, including the newline character.

  

f = open("test.txt", "r")

f.readline()

'This is a First File\n'

  

f.readline()

'Contains two lines\n'

  

f.readline()

''”

The readlines() method returns a list of remaining lines of the entire file. All these reading methods return empty values when the end of file (EOF) is reached.

  

f.seek(0)

  

f.readlines()

['This is a First File\n', 'Contains two lines\n']

  
  

#### Renaming And Deleting Files In Python.

  

While you were using the read/write functions, you may also need to rename/delete a file in Python. So, there comes a os module in Python which brings the support of file rename/delete operations.

So, to continue, first of all, you should import the os module in your Python script.

  

import os

​

#Rename a file from test.txt to sample.txt

os.rename("test.txt", "sample.txt")

  

f = open("sample.txt", "r")

f.readline()

'This is a First File\n'

  

#Delete a file sample.txt

os.remove("sample.txt")

  

f = open("sample.txt", "r")

f.readline()

---------------------------------------------------------------------------

FileNotFoundError                         Traceback (most recent call last)

<ipython-input-25-6eeb6c12a935> in <module>()

----> 1 f = open("sample.txt", "r")

      2 f.readline()

  

FileNotFoundError: [Errno 2] No such file or directory: 'sample.txt'

  
  

### Python Directory and File Management

  

If there are a large number of files to handle in your Python program, you can arrange your code within different directories to make things more manageable.

A directory or folder is a collection of files and sub directories. Python has the os module, which provides us with many useful methods to work with directories (and files as well).

Get current Directory

We can get the present working directory using the getcwd() method. This method returns the current working directory in the form of a string.

  

  

import os

os.getcwd()

'/Users/varma/Google Drive/OnlineVideos/2/python-basics/File Operation'

  

#### Changing Directory

We can change the current working directory using the chdir() method.

The new path that we want to change to must be supplied as a string to this method. We can use both forward slash (/) or the backward slash () to separate path elements.

  

os.chdir("/home/nishant/")

  

os.getcwd()

'/home/nishant

  

#### List Directories and Files

All files and sub directories inside a directory can be known using the listdir() method.

  

os.listdir(os.getcwd())

['.bash_history',

 '.bash_sessions',

 '.bashrc',....etc']

  
  

#### Making New Directory

We can make a new directory using the mkdir() method.

This method takes in the path of the new directory. If the full path is not specified, the new directory is created in the current working directory.

  

os.mkdir('test')

  

However, note that rmdir() method can only remove empty directories.

In order to remove a non-empty directory we can use the rmtree() method inside the shutil module.

  

os.rmdir('test')

In [0]:

import shutil

​

os.mkdir('test')

os.chdir('./test')

f = open("testfile.txt",'w')

f.write("Hello World")

os.chdir("../")

os.rmdir('test')

​

---------------------------------------------------------------------------

OSError                                   Traceback (most recent call last)

<ipython-input-39-a990945f349d> in <module>()

      6 f.write("Hello World")

      7 os.chdir("../")

----> 8 os.rmdir('test')

      9 

     10 

  

OSError: [Errno 66] Directory not empty: 'test'

  
  

# remove an non-empty directory

shutil.rmtree('test')

  

os.getcwd()

'/home/nishant'

  

### Exception Handling:

#### Python Errors and Built-in-Exceptions

When writing a program, we, more often than not, will encounter errors.

Error caused by not following the proper structure (syntax) of the language is called syntax error or parsing error.

  

if a < 3

 File "<ipython-input-1-3e28e520013d>", line 1

    if a < 3

            ^

SyntaxError: invalid syntax

  
  
  

Errors can also occur at runtime and these are called exceptions.

  
  

1 / 0

  

ZeroDivisionError                         Traceback (most recent call last)

<ipython-input-3-b710d87c980c> in <module>()

----> 1 1 / 0

ZeroDivisionError: integer division or modulo by zero

  

open('test.txt')

---------------------------------------------------------------------------

  

IOError                                   Traceback (most recent call last)

<ipython-input-4-46a2b0c9e87f> in <module>()

----> 1 open('test.txt')

IOError: [Errno 2] No such file or directory: 'test.txt'

  

#### Python Built-in Exceptions

  

dir(__builtins__)

  

['ArithmeticError',

 'AssertionError',

 'AttributeError',

 'BaseException'

…

...etc]

  

#### Python Exception Handling - Try, Except and Finally

  

Python has many built-in exceptions which forces your program to output an error when something in it goes wrong.

When these exceptions occur, it causes the current process to stop and passes it to the calling process until it is handled. If not handled, our program will crash.

For example, if function A calls function B which in turn calls function C and an exception occurs in function C. If it is not handled in C, the exception passes to B and then to A.

If never handled, an error message is spit out and our program come to a sudden, unexpected halt.

#### Catching Exceptions in Python

In Python, exceptions can be handled using a try statement.

A critical operation which can raise an exception is placed inside the try clause and the code that handles exception is written in the except clause.

  

# import module sys to get the type of exception

import sys

​

lst = ['b', 0, 2]

​

for entry in lst:

   try:

       print("The entry is", entry)

       r = 1 / int(entry)

   except:

       print("Oops!", sys.exc_info()[0],"occured.")

       print("Next entry.")

       print("***************************")

print("The reciprocal of", entry, "is", r)

The entry is b

Oops! <class 'ValueError'> occured.

Next entry.

***************************

The entry is 0

Oops! <class 'ZeroDivisionError'> occured.

Next entry.

***************************

The entry is 2

The reciprocal of 2 is 0.5

  

#### Catching Specific Exceptions in Python

In the above example, we did not mention any exception in the except clause.

This is not a good programming practice as it will catch all exceptions and handle every case in the same way. We can specify which exceptions an except clause will catch.

A try clause can have any number of except clauses to handle them differently but only one will be executed in case an exception occurs.

import sys

​

lst = ['b', 0, 2]

​

for entry in lst:

   try:

       print("****************************")

       print("The entry is", entry)

       r = 1 / int(entry)

   except(ValueError):

       print("This is a ValueError.")

   except(ZeroDivisionError):

       print("This is a ZeroError.")

   except:

       print("Some other error")

print("The reciprocal of", entry, "is", r)

****************************

The entry is b

This is a ValueError.

****************************

The entry is 0

This is a ZeroError.

****************************

The entry is 2

The reciprocal of 2 is 0.5

  

#### Raising Exceptions

In Python programming, exceptions are raised when corresponding errors occur at run time, but we can forcefully raise it using the keyword raise.

We can also optionally pass in value to the exception to clarify why that exception was raised.

  
  

try:

   num = int(input("Enter a positive integer:"))

   if num <= 0:

       raise ValueError("Error:Entered negative number")

except ValueError as e:

   print(e)

Enter a positive integer:-10

Error:Entered negative number

  

#### try ... finally

The try statement in Python can have an optional finally clause. This clause is executed no matter what, and is generally used to release external resources.

  

try:

   f = open('sample.txt')

   #perform file operations

except:

   #handle exception

finally:

   f.close()

---------------------------------------------------------------------------

FileNotFoundError                         Traceback (most recent call last)

<ipython-input-2-80e1a41ea167> in <module>

      1 try:

----> 2     f = open('sample.txt')

      3     #perform file operations

FileNotFoundError: [Errno 2] No such file or directory: 'sample.txt'

  

During handling of the above exception, another exception occurred:

  

NameError                                 Traceback (most recent call last)

<ipython-input-2-80e1a41ea167> in <module>

      4 

      5 finally:

----> 6     f.close()

      7     print('h')

NameError: name 'f' is not defined

  
  
  

4.10 Debugging Python

pdb implements an interactive debugging environment for Python programs. It includes features to let you pause your program, look at the values of variables, and watch program execution step-by-step, so you can understand what your program actually does and find bugs in the logic.

### Starting the Debugger

  
  

#### From the Command Line

  

import pdb

​

#interactive debugging

def seq(n):

   for i in range(n):

       pdb.set_trace() # breakpoint

       print(i)

   return

​

seq(5)

  

​

  

#### Debugger Commands

1. h(elp) [command]

Without argument, print the list of available commands. With a command as argument, print help about that command. help pdb displays the full documentation (the docstring of the pdb module). Since the command argument must be an identifier, help exec must be entered to get help on the ! command.

2. w(here)

Print a stack trace, with the most recent frame at the bottom. An arrow indicates the current frame, which determines the context of most commands.

3. d(own) [count]

Move the current frame count (default one) levels down in the stack trace (to a newer frame).

4.c(ont(inue))

Continue execution, only stop when a breakpoint is encountered.

5. q(uit)

Quit from the debugger. The program being executed is aborted.