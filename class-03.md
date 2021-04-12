# HTML 

## Chapter 3 

### Lists 

> three different types of lists:

| type | definition | 
|------|------------|
|Ordered lists | are lists where each item in the list is numbered   |
|Unordered lists | are lists that begin with a bullet point |
|Definition lists | are made up of a set of terms along with the definition for each of those terms |

* Ordered Lists: 

1. (ol)

*The ordered list is created with
the (ol) element.* 

2. (li)

*Each item in the list is placed
between an opening (li) tag
and a closing (/li) tag. (The li
stands for list item.)*

* Unordered Lists: 

1. (ul)

*The unordered list is created
with the (ul) element.*

2. (li)

*Each item in the list is placed
between an opening (li) tag
and a closing (/li) tag. (The li
stands for list item.)*

* Definition Lists:

1. (dl)

*The definition list is created with
the (dl) element and usually
consists of a series of terms and
their definitions.
Inside the (dl) element you will
usually see pairs of (dt) and
(dd) elements.*

2. (dt)

*This is used to contain the term
being defined (the definition
term).*

3. (dd)

*This is used to contain the
definition.*

>- All of tags write between <>

## Chapter 13
 
### Boxes

> Box Dimensions

***By default a box is sized just big
enough to hold its contents. To
set your own dimensions for a
box you can use the height and
width properties.*** 

* When you use percentages,
the size of the box is relative to
the size of the browser window

* When you use ems, the size
of the box is based on the size
of text within it.

> Border

***Every box has a border (even if
it is not visible or is specified to
be 0 pixels wide). The border
separates the edge of one box
from another.*** 

* border-width 

*The border-width property
is used to control the width
of a border.*

* border-style 

*You can control the style of a
border using the border-style
property.* 

* border-color

*You can specify the color of a
border using either RGB values,
hex codes or CSS color names.*


> Margin

***Margins sit outside the edge
of the border. You can set the
width of a margin to create a
gap between the borders of two
adjacent boxes.*** 

> Padding 

***Padding is the space between
the border of a box and any
content contained within it.
Adding padding can increase the
readability of its contents.***

* ***"The padding and
margin properties
are very helpful
in adding space
between various
items on the page."*** 

# JAVASCRIPT 

## Chapter 2 

### Basic JavaScript Instructions 

> CREATING AN ARRAY 

* VALUES IN ARRAYS 

1. The values are assigned to the
array inside a pair of square
brackets, and each value is
separated by a comma. The
values in the array do not need
to be the same data type, so you
can store a string, a number and
a Boolean all in the same array.

2. Values in an array are accessed as if they are in
a numbered list. It is important to know that the
numbering of this list starts at zero (not one). 

* NUMBERING ITEMS IN AN ARRAY 
 
 *Each item in an array is
automatically given a number
called an index. This can be used
to access specific items in the
array.* 

* ACCESSING ITEMS IN AN ARRAY 

*To retrieve the third item on the
list, the array name is specified
along with the index number in
square brackets.* 

* NUMBER OF ITEMS IN AN ARRAY 

*Each array has a property called
length, which holds the number
of items in the array.* 


## Chapter 4

### Decisions and Loops 

> IF ELES STATEMENTS 

***The if/else statement executes a block of code if a specified condition is true. If the condition is false, another block of code can be executed.***

***The if/else statement is a part of JavaScript's "Conditional" Statements, which are used to perform different actions based on different conditions.*** 

> USING IF ... ELSE STATEMENTS 

**if ... e1se statement allows you to provide two sets of code:**
1. one set if the condition
evaluates to true

2. another set if the condition is
false 

![if...else](https://www.tutorialspoint.com/cprogramming/images/if_else_statement.jpg) 

> SWITCH STATEMENTS 

***A switch statement starts with a
variable called the switch value.
Each case indicates a possible
value for this variable and the
code that should run if the
variable matches that value.*** 

> TRUTHY & FALSY VALUES 

***Due to type coercion, every value in JavaScript
can be treated as if it were true or false; and
this has some interesting side effects.*** 

* Falsy values are treated as if they are fa1se. 

*Falsy values can also be treated as the number 0 .* 

* Truthy values are treated as if they are true. 

*Truthy va lues can also be treated as the number 1.* 

>Logical operators 

***operators that combine multiple boolean expressions or values and provide a single boolean output. The operators include: &&, ||, and !.***  

> for and while loops 

***It was previously described in Class-02 on Reading-notes*** 


