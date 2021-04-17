# JAVASCRIPT 

## Chapter 3

### Object Literals 

> WHAT IS AN OBJECT ? 

***Objects group together a set of variables and functions to create a model
of a something you would recognize from the real world. In an object,
variables and functions take on new names.*** 

> CREATING AN OBJECT: LITERAL NOTATION 

**literal notation is the easiest and most popular way to create objects** 

> CREATING· OBJECTS USING LITERAL NOTATION 

**This object is called hotel which
represents a hotel called Quay
with 40 rooms (25 of which have
been booked).** 

**Next, the content of the page
is updated with data from this
object. It shows the name of the
hotel by accessing the object's
name property and the number
of vacant rooms using the
checkAvail ability() method.** 

**To access a property of this
object, the object name is
followed by a dot (the period
symbol) and the name of the
property that you want.**

**Similarly, to use the method,
you can use the object name
followed by the method name.
hotel .checkAvailability()**

**If the method needs parameters,
you can supply them in the
parentheses (just like you can
pass arguments to a funct ion).** 

## Chapter 5

### Document Object Model

***The Document Object Model (DOM) specifies
how browsers should create a model of an HTML
page and how JavaScript can access and update the
contents of a web page while it is in the browser window***   

> MAKING A MODEL OF THE HTML PAGE 

**When the browser loads a web page, it
creates a model of the page in memory.
The DOM specifies the way in which the
browser should structure this model using
a DOM tree.
The DOM is called an object model
because the model (the DOM tree) is
made of objects.
Each object represents a different part of
the page loaded in the browser window.** 

> ACCESSING AND CHANGING THE HTML PAGE 

**The DOM also defines methods and
properties to access and update each
object in this model, which in turn updates
what the user sees in the browser.
You will hear people call the DOM an
Application Programming Interface (API).
User interfaces let humans interact with
programs; APls let programs (and scripts)
talk to each other. The DOM states what
your script can "ask the browser about the
current page, and how to tell the browser
to update what is being shown to the user.** 

> THE DOM TREE IS A MODEL OF A WEB PAGE 

**As a browser loads a web page, it creates a model of that page.
The model is called a DOM tree, and it is stored in the browsers' memory.
It consists of four main types of nodes.**

* THE DOCUMENT NODE 

*Every element, attribute, and piece of text in the
HTML is represented by its own DOM node.
At the top of the tree a document node is added; it
represents the entire page, When you access any element, attribute, or text
node, you navigate to it via the document node. It is
the starting point for all visits to the DOM tree.* 

* ELEMENT NODES 

*HTML elements describe the structure of an HTML
page. (The (h l ) - (h6) elements describe what
parts are headings; the (p) tags indicate where
paragraphs of text start and finish; and so on.)
To access the DOM tree, you start by looking for
elements. Once you find the element you want, then
you can access its text and attribute nodes if you
want to. This is why you start by learning methods
that allow you to access element nodes, before
learning to access and alter text or attributes.* 

" the elements write between <> " 

* ATTRIBUTE NODES 

*The opening tags of HTML elements can carry
attributes and these are represented by attribute
nodes in the DOM tree.
Attribute nodes are not children of the element thar
carries them; they are part of that element.* 

* TEXT NODES 

*Once you have accessed an element node, you
can then reach the text within that element. This is
stored in its own text node.
Text nodes cannot have children. If an element
contains text and another child element, the child
element is not a child of the text node but rather
a child of the containing element.* 

![dom tree](https://1.bp.blogspot.com/-Z0QnE9eWAnM/XWj6B0TmfmI/AAAAAAAAZps/aRfAU517hg0ovfzgLUTZkmjHD3SXZCoWACLcBGAs/s640/DOM.PNG)

> WORKING WITH THE DOM TREE 

* Accessing and updating the DOM tree involves two steps:

1. Locate the node that represents the element you want to work with.

2. Use its text content, child elements, and attributes.

> ACCESSING ELEMENTS 

*DOM queries may return one element, or they may return a Nodelist,
which is a collection of nodes.* 

> TRAVERSING THE DOM 

*When you have an element node, you can select
another element in relation to it using these five
properties. This is known as traversing the DOM.* 

![TRAVERSING THE DOM](https://data-flair.training/blogs/wp-content/uploads/sites/2/2019/08/traversing-between-element-nodes.png)


> WHITESPACE NODES 

*Traversing the DOM can be difficult because
some browsers add a text node whenever they
come across whitespace between elements.* 

![WHITESPACE NODES](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT5bxJ-qk-Rb27I-5PZmFniOhGYZEYflVcuRg&usqp=CAU)

> ACCESS & UPDATE A TEXT NODE WITH NODEVALUE 

*When you select a text node, you can retrieve or amend the content of it
using the node Va 1 ue property.* 

> ACCESS & UPDATE TEXT WITH TEXTCONTENT (& INN ERTEXT)  

*The textCon tent property allows you to
collect or update just the text that is in the
containing element (and its children).*

> ADDING ELEMENTS USING DOM MANIPULATION 

| step num | the step | 
|----------|----------| 
| 1        | CREATE THE ELEMENT |
| 2        | GIVE IT CONTENT    |
| 3        | ADD IT TO THE DOM  | 

> EXAMINING THE DOM IN CHROME 

*Modern browsers come with tools that help
you inspect the page loaded in the browser
and understand the structure of the DOM tree.* 

> EXAMINING THE DOM IN FIREFOX 

*Firefox has similar built-in tools, but you can
also download a DOM inspector tool that
shows the text nodes.* 

