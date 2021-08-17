# Automation 

## Python Regular Expressions Tutorial 

### Regular Expressions in Python 

***In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import:*** 

        import re 

***The re library in Python provides several functions that make it a skill worth mastering.***

### Basic Patterns: Ordinary Characters

***can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax.***

*Examples :*

        'A', 'a', 'X', '5'.

### Wild Card Characters: Special Characters 

***Special characters are characters that do not match themselves as seen but have a special meaning when used in a regular expression.*** 

### Repetitions

***the re module handles repetitions using the special characters*** 

### Grouping in Regular Expressions 

***The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis are called groups. The parenthesis does not change what the expression matches, but rather forms groups within the matched sequence.***

### Summary table 

 	
| Character(s) | What it does |
| ----------- | ----------- |
| . |  	A period. Matches any single character except the newline character. |
| ^ |  	A caret. Matches a pattern at the start of the string. |
| \A |  Uppercase A. Matches only at the start of the string. |
| $ |  	Dollar sign. Matches the end of the string. |
| \Z |  Uppercase Z. Matches only at the end of the string. |
| [ ] | Matches the set of characters you specify within it. |
| \ |  If the character following the backslash is a recognized escape character, special meaning of term is taken. |
| \w | Lowercase w. Matches any single letter, digit, or underscore. |
| \W | Uppercase W. Matches any character not part of \w (lowercase w). |
| \s | Lowercase s. Matches a single whitespace character like: space, newline, tab, return. |
| \S | Uppercase S. Matches any character not part of \s (lowercase s). |
| \d | Lowercase d. Matches decimal digit 0-9. |
| \D | Uppercase D. Matches any character that is not a decimal digit. |
| \t | Lowercase t. Matches tab. |
| \n | Lowercase n. Matches newline. |
| \r | Lowercase r. Matches return. |
| \b | Lowercase b. Matches only the beginning or end of the word. |
| + | Checks if the preceding character appears one or more times. |
| * | Checks if the preceding character appears zero or more times. |
| ? | Checks if the preceding character appears exactly zero or one time.  |
| { } | Checks for an explicit number of times. |
| ( ) | Creates a group when performing matches. |
| < > | Creates a named group when performing matches. |

### Function provided by 're' 

***The re library in Python provides several functions to make your tasks easier. such as the re.search(), re.match().***

## shutil 

***The shutil module includes high-level file operations such as copying and archiving.*** 

### Copying Files 

**copyfile() copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.** 

### Copying File Metadata 

**By default when a new file is created under Unix, it receives permissions based on the umask of the current user. To copy the permissions from one file to another, use copymode().**

### Working With Directory Trees 

**shutil includes three functions for working with directory trees. To copy a directory from one place to another, use copytree(). It recurses through the source directory tree, copying files to the destination. The destination directory must not exist in advance.**

### Finding Files 

**The which() function scans a search path looking for a named file. The typical use case is to find an executable program on the shell’s search path defined in the environment variable PATH.**

### Archives 

**Python’s standard library includes many modules for managing archive files such as tarfile and zipfile. There are also several higher-level functions for creating and extracting archives in shutil. get_archive_formats() returns a sequence of names and descriptions for formats supported on the current system.**

### File System Space 

**It can be useful to examine the local file system to see how much space is available before performing a long running operation that may exhaust that space. disk_usage() returns a tuple with the total space, the amount currently being used, and the amount remaining free.**