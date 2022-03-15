# Reading_Notes
## Readings: Game of Greed 3, List Comprehensions and Decorators.

By [Ghaida Al Momani] (https://github.com/GhaidaMomani).

>>>>>Welcome to Code 401.
<br/>
<hr/>
<br/>


**Syntax**
Consider the following example:

```
my_new_list = [ expression for item in list ]
```
You can see from this example that three ingredients are necessary for a python list comprehension to work.

* First is the expression we’d like to carry out. expression inside the square brackets.
* Second is the object that the expression will work on. item inside the square brackets.
* Finally, we need an iterable list of objects to build our new list from. list inside the square brackets.

 ## Create a List with range()
```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

```

**output**
```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

<p align="right">(<a href="#top">back to top</a>)</p>

**Example 2: Comparing list creation methods in Python**

First, create a list and loop through it. Add an expression, in this example, we’ll raise x to the power of 2.

# create a list using a for loop
```
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
```
**output**
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
## Multiplying Parts of a List

```
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)

```
**output**
```
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]

```
<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>


## Show the first letter of each word using Python

```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)

```

**output**
```
['E', 'L', 'F', 'T', 'E', 'S']

```

## Lower/Upper case converter using Python

```
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
```
```
['a', 'b', 'c'] ['A', 'B', 'C']
```
## Print numbers only from a given string
```
# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
```
**Output**
```
['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```
## Parsing a file using list comprehension
```
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
 ```
Output
```
Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
```
# In conclusion
Hopefully you’ve seen the potential of list comprehensions and how they can be used to write more elegant Python code. Writing compact code is essential for maintaining programs and working with teams. 
 <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 15 MAR </p>