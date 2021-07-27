> # FileIO & Exceptions

# Read & Write Files in Python 

### What Is a File ?

***At its core, a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.*** 

> Files on most modern file systems are composed of three main parts:

* Header: 

*metadata about the contents of the file (file name, size, type, and so on)*

* Data: 

*contents of the file as written by the creator or editor*

* End of file (EOF): 

*special character that indicates the end of the file* 

![modern file](https://files.realpython.com/media/FileFormat.02335d06829d.png) 

> File Paths : 


* Folder Path: 

*the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)*

* File Name: 

*the actual name of the file*

* Extension: 

*the end of the file path pre-pended with a period (.) used to indicate the file type*

**For Example :** 

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

### Opening and Closing a File in Python : 

**When you want to work with a file,  open() has a single required argument that is the path to the file.open() has a single return** 

     file = open('dog_breeds.txt')

***You should always make sure that an open file is properly closed.*** 

**When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error.**

*The first way to close a file is to use the try-finally block:* 


     reader = open('dog_breeds.txt')

     try:

     # Further file processing goes here finally:

     reader.close()

*The second way to close a file is to use the with statement:* 

      with open('dog_breeds.txt') as reader:
      # Further file processing goes here

### There are three different categories of file objects : 

1. Text files
1. Buffered binary files
1. Raw binary files

> Text File Types : 

**A text file is the most common file that you’ll encounter. With these types of files, open() will return a TextIOWrapper file object, This is the default file object returned by open().** 

*Example :* 

     >>> file = open('dog_breeds.txt')
     >>> type(file)

> Buffered Binary File Types : 

**A buffered binary file type is used for reading and writing binary files. With these types of files, open() will return either a BufferedReader or BufferedWriter file object** 

*Example :* 

      >>> file = open('dog_breeds.txt', 'rb')
      >>> type(file)
      <class '_io.BufferedReader'>
      >>> file = open('dog_breeds.txt', 'wb')
      >>> type(file)
      <class '_io.BufferedWriter'>

> Raw File Types 

**"generally used as a low-level building-block for binary and text streams.", It is therefore not typically used. With these types of files, open() will return a FileIO file object** 

*Example :* 

     >>> file = open('dog_breeds.txt', 'rb', buffering=0)
     >>> type(file)
     <class '_io.FileIO'>

# Exceptions in Python 

***A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception.*** 

### Exceptions versus Syntax Errors 

**Syntax errors occur when the parser detects an incorrect statement.** 

*Example :*

     >>> print( 0 / 0 ))
     File "<stdin>", line 1
     print( 0 / 0 ))
                  ^
     SyntaxError: invalid syntax

### Raising an Exception 

**We can use raise to throw an exception if a condition occurs.**

![Raising an Exception](https://files.realpython.com/media/raise.3931e8819e08.png) 

### The AssertionError Exception 

**Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.** 

![The AssertionError Exception](https://files.realpython.com/media/assert.f6d344f0c0b4.png)  

### The try and except Block: Handling Exceptions 

**The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.** 

![The try and except Block: Handling Exceptions](https://files.realpython.com/media/try_except.c94eabed2c59.png) 

### The else Clause 

**In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.**

![The else Clause](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)  

### Cleaning Up After Using finally 

**you implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.** 

![Cleaning Up After Using finally ](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)   


