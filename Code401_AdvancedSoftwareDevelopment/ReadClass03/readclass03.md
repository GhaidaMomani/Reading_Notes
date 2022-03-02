# Reading_Notes
## Code 401 - Advanced Software Development
## File IO & Exceptions
<!-- This is the reading notes repository where I keep my favorite articles with their sources.
       
       Hope you'll benefit from my reads, Enjoy!
-->




By [Ghaida Al Momani] (https://github.com/GhaidaMomani).
<br/>
<hr/>
<br/>


## Description
**File IO & Exceptions** 

Below you will find a sammary for the Read Class 03material, code samples, and some additional resources that support it'stopic.





<hr/>
<br/>


## Reading and Writing Files in Python

What you should know to make operations over files in python:
* What makes up a file and why that’s important in Python
* The basics of reading and writing files in Python
* Some basic scenarios of reading and writing files


# What Is a File?
 a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.

**Files on most modern file systems are composed of three main parts:**

[1] **Header:** metadata about the contents of the file (file name, size, type, and so on)

[2] **Data:** contents of the file as written by the creator or editor.

[3] **End of file (EOF):** special character that indicates the end of the file


# File Paths
This is what you use to access any file, The file path is a string that represents the location of a file. It’s broken up into three major parts:

[1] Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)

[2] File Name: the actual name of the file
Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

```

/
│
├── path/
|   │
│   ├── to/
│   │   └── cats.gif
│   │
│   └── dog_breeds.txt
|
└── animals.csv


```
<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>

<!-- ROADMAP -->
# Dealing with files (Open, Close ,Read, Write)
## Opening and Closing a File in Python
**When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file.**

```

file = open('dog_breeds.txt')
```


```python
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

* **with statement:** An alternative way of doing this is using with statements. This creates a temporary variable (often called f), which is only accessible in the indented block of the with statement.
```python
with open("filename.txt") as f:
   print(f.read())
```

### You can specify the mode used to open a file by applying a second argument to the open function.

- [1] Sending "r" means open in read mode, which is the default.
- [2] Sending "w" means write mode, for rewriting the contents of a file.
- [3] Sending "a" means append mode, for adding new content to the end of the file.

- [4] Adding "b" to a mode opens it in binary mode, which is used for non-text files (such as image and sound files).





There are three different categories of file objects:

* Text files
* Buffered binary files
* Raw binary files
 
<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>

# Python Exceptions: An Introduction

**exception error** This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.

Instead of showing the message exception error, Python details what type of exception error was encountered. In this case, it was a ZeroDivisionError. Python comes with various built-in exceptions as well as the possibility to create self-defined exceptions.




**Raising an Exception**

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))


```

**The try and except Block: Handling Exceptions**
```
def linux_interaction():
    assert ('linux' in sys.platform), "Function can only run on Linux systems."
    print('Doing something.')
```

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
    print('The linux_interaction() function was not executed')
```






<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>
  <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 2 MAR </p>