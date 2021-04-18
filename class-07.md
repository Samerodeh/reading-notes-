# Domain Modeling 

**Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.** 

> Define a constructor and initialize properties 

*To define the same properties between many objects, you'll want to use a constructor function.* 

> Generate random numbers 

*To model the random nature of user behavior, you'll need the help of a random number generator. Fortunately, the JavaScript standard library includes a Math.random() function for just this sort of occasion.* 

# HTML 

## Chapter 6 

### Tables 

***There are several types of information
that need to be displayed in a grid or
table. For example: sports results, stock
reports, train timetables.*** 

> What's a Table?

*A table represents information in a grid format.
Examples of tables include financial reports, TV
schedules, and sports results.* 

> Basic Table Structure 

* (table)

The (table) element is used
to create a table. The contents
of the table are written out row
by row.

* (tr)

You indicate the start of each
row using the opening (tr) tag.
(The tr stands for table row.)
It is followed by one or more
(td) elements (one for each cell
in that row).
At the end of the row you use a
closing (/tr) tag.

* (td)

Each cell of a table is
represented using a (td)
element. (The td stands for
table data.)
At the end of each cell you use a
closing (/td) tag. 

" All tags write between <> " 

> Table Headings 

* (th)

The (th) element is used just
like the (td) element but its
purpose is to represent the
heading for either a column or
a row. (The th stands for table
heading.) 

" Tag write between <> " 

> Spanning ColumnS 

*Sometimes you may need the
entries in a table to stretch
across more than one column.* 

*The colspan attribute can be
used on a (th) or (td) element
and indicates how many columns
that cell should run across.* 

" Tags write between <> "  

> Spanning Rows 

*You may also need entries in
a table to stretch down across
more than one row.*

*The rowspan attribute can be
used on a (th) or (td) element
to indicate how many rows a cell
should span down the table.* 

" Tags write between <> "

> Long Tables  

* (thead)

*The headings of the table should
sit inside the (thead) element.* 

* (tbody)

*The body should sit inside the
(tbody) element.* 

* (tfoot)

*The footer belongs inside the
(tfoot element.* 

# JAVASCRIPT 

## Chapter 3

### Functions, Methods, and Objects 

> CREATING AN OBJECT: 

**CONSTRUCTOR NOTATION The new keyword and the object constructor create a blank object. You can then add properties and methods to the object** 

> UPDATING AN OBJECT 

**To update the value of properties, use dot notation or square braçkets. They work on objects created using literal or constructor notation. To delete a property, use the delete keyword** 

> CREATING MANY OBJECTS: 

**CONSTRUCTOR NOTATION Sometimes you will want several objects to represent similar things. Object constructors can use a function as a template for creating objects. + First, create the template with the object's properties and methods.** 

***You create instances of the object using the constructor function. The new keyword followed by a call to the function creates a new object. The properties of each object are given as arguments to the function.***  

> THIS (IT IS A KEYWORD) 

*The keyword this is commonly used inside functions and objects.
Where the function is declared alters what this means. It always refers
to one object, usually the object in which the function operates.* 

> RECAP: STORING DATA 

*In JavaScript, data is represented using name/value pairs.
To organize your data, you can use an array or object to group a set of
related values. In arrays and objects the name is also known as a key.* 

* VARIABLES 

*A variable has just one key (the variable name)
and one va lue.* 

* ARRAYS 

*Arrays can store multiple pieces of information.
Each piece of information is separated by a comma.
The order of the values is important because items
in an array are assigned a number* 

***If you want to access items via a property name or key, use an object
(but note that each key in the object must be unique).
If the order of the items is important, use an array.*** 

> ARRAYS ARE OBJECTS 

**Arrays are actually a special type of object. They hold a related set of key/value pairs (like all objects), but the key for each value is its index number.** 

> ARRAYS OF OBJECTS & OBJECTS IN ARRAYS

***You can combine arrays and objects to create complex data structures: Arrays can store a series of objects (and remember their order). Objects can also hold arrays (as values of their properties).***

> WHAT ARE BUILT-IN OBJECTS?  

*Browsers come with a set of built-in objects that represent things like the
browser window and the current web page shown in that window. These
built-in objects act like a toolkit for creating interactive web pages.* 

> The first thing you need to do is get to know what tools are available.
You can imagine that your new toolkit has three compartments: 

1. BROWSER OBJECT MODEL

The Browser Object Model contains
objects that represent the current
browser window or tab. It contains
objects that model things like
browser history and the
device's screen.

2. DOCUMENT OBJECT MODEL

The Document Object Model uses
objects to create a representation of
the current page. It creates a new
object for each element (and each
individual section of text)
within the page. 

3. GLOBAL JAVASCRIPT OBJECTS

The global JavaScript objects
represent things that the JavaScript
language needs to create a model
of. For example, there is an
object that deals only with
dates and times.

***Each character in a string is automatically given a number, called an index
number. Index numbers always start at zero and not one (just like for
items in an array).*** 

> DATA TYPES REVISITED 

*In JavaScript there are six data types:
Five of them are described as simple (or primitive) data types.
The sixth is the object (and is referred to as a complex data type).* 

> GLOBAL OBJECTS: NUMBER OBJECT 

*Whenever you have a value that is a number,
you can use the methods and properties of the
Number object on it.* 

> GLOBAL OBJECTS: MATH OBJECT 

*The Math object has properties and methods
for mathematical constants and functions.* 

> GLOBAL OBJECTS: DATE OBJECT (AND TIME) 

*Once you have created a Date object, the following methods let you set
and retrieve the time and date that it represents.* 









