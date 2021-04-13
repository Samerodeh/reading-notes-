# HTML 

## Chapter 4

### Links 

> Linking to Other Sites 

(a) 

*Links are created using the (a)
element which has an attribute
called href. The value of the
href attribute is the page that
you want people to go to when
they click on the link.* 

*When you link to a different
website, the value of the href
attribute will be the full web
address for the site, which is
known as an absolute URL.*

* a element write between <>  

> Linking to Other Pages on the Same Site 

(a)

*When you are linking to other
pages within the same site,
you do not need to specify the
domain name in the URL. You
can use a shorthand known as a
relative URL.* 

* a element write between <>  

> Rela tive URLs 

*Relative URLs can be used when linking to pages within your own
website. They provide a shorthand way of telling the browser where to
find your files.*

> Email Links

* mailto: 

*To create a link that starts up
the user's email program and
addresses an email to a specified
email address, you use the (a)
element. However, this time the
value of the href attribute starts
with mailto: and is followed by
the email address you want the
email to be sent to.*  

> Op ening Links in a New Window 

* target 

*If you want a link to open in a
new window, you can use the
target attribute on the opening
(a) tag. The value of this
attribute should be _blank.* 

> Linking to a Sp ecific Part of the Sa me Page 

*you need to
identify the points in the page
that the link will go to. You do
this using the id attribute (which
can be used on every HTML
element). You can see that the
(h1) and (h2) elements in this
example have been given id
attributes that identify those
sections of the page.*

> Linking to a Sp ecific Part of Another Page 

*If you want to link to a specific
part of a different page (whether
on your own site or a different
website) you can use a similar
technique.*

*As long as the page you are
linking to has id attributes that
identify specific parts of the
page, you can simply add the
same syntax to the end of the
link for that page.* 

# CSS 

## Chapter 15 

### Layout

#### Key Concepts in Positioning Elements 

> Building Blocks 

* CSS treats each HTML element as if it is in its
own box. This box will either be a block-level
box or an inline box. 

1. Block-level elements

*start on a new line
Examples include:
(h1) (p) (ul) (li)* 

* the elements write between <> 

2. Inline elements

*flow in between
surrounding text
Examples include:
(img) (b) (i)* 

> Containing Elements 

**If one block-level element sits inside another
block-level element then the outer box is
known as the containing or parent element.** 

> Controlling the Position of Elements 

* Normal flow 

**Every block-level element
appears on a new line, causing
each item to appear lower down
the page than the previous one.
Even if you specify the width
of the boxes and there is space
for two elements to sit side-byside,
they will not appear next
to each other. This is the default
behavior (unless you tell the
browser to do something else).** 

* Relative Positioning 

**This moves an element from the
position it would be in normal
flow, shifting it to the top, right,
bottom, or left of where it
would have been placed. This
does not affect the position of
surrounding elements; they stay
in the position they would be in
in normal flow.** 

* Absolute positioning 

**This positions the element
in relation to its containing
element. It is taken out of
normal flow, meaning that it
does not affect the position
of any surrounding elements
(as they simply ignore the
space it would have taken up).
Absolutely positioned elements
move as users scroll up and
down the page.** 

* Fixed Positioning 

**This is a form of absolute
positioning that positions
the element in relation to the
browser window, as opposed
to the containing element.
Elements with fixed positioning
do not affect the position of
surrounding elements and they
do not move when the user
scrolls up or down the page.** 

* Floating Elements 

**Floating an element allows
you to take that element out
of normal flow and position
it to the far left or right of a
containing box. The floated
element becomes a block-level
element around which other
content can flow.** 

> Screen Sizes 

***Different visitors to your site will have different sized screens that show
different amounts of information, so your design needs to be able to
work on a range of different sized screens.*** 

> Screen Resolution 

***Resolution refers to the number of dots a screen shows per inch. Some
devices have a higher resolution than desktop computers and most
operating systems allow users to adjust the resolution of their screens.*** 

> Page Sizes 

***Because screen sizes and display resolutions vary so much, web
designers often try to create pages of around 960-1000 pixels wide
(since most users will be able to see designs this wide on their screens).*** 

> Fixed Width Layouts 

***Fixed width layout
designs do not
change size as the
user increases
or decreases
the size of their
browser window.
Measurements tend
to be given in pixels.*** 

> Liquid Layouts 

***Liquid layout designs
stretch and contract
as the user increases
or decreases the
size of their browser
window. They tend to
use percentages.*** 

# JAVASCRIPT 

## Chapter 3 

### Functions, Methods, and Objects 

> FUNCTIONS & METHODS 

***Functions consist of a series of statements that have been grouped together because they perform a specific task. A method is the same as a function, except methods are created inside (and are part of) an object.*** 

> OBJECTS 

***programmers use objects to create models of the world using data, and that objects are made up of properties and methods. In this section, you learn how to create your own objects using JavaScript. 

> BUILT-IN OBJECTS 

***The browser comes with a set of objects that act like a toolkit for creating interactive web pages. This section introduces you to a number of built-in objects, which you will then see used throughout the rest of the book.*** 

## WHAT IS A FUNCTION ? 

* Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of st atements). 

## ECLARING A FUNCTION 

* To create a function, you give it a name and then write the statements needed to achieve its task inside the curly braces. This is known as a function declaration. 

## CALLING A FUNCTION 

* Having declared the function, you can then execute all of the statements between its curly braces with just one line of code. This is known as calling the function.

## ANONYMOUS FUNCTIONS & FUNCTION EXPRESSIONS 

* Expressions produce a value. They can be used where values are expected.
If a function is placed where a browser expects to see an expression, then it gets treated as an expression.

## IMMEDIATELY INVOKED FUNCTION EXPRESSIONS 

* This way of writing a function is used in several different situations.
Often functions are used to ensure that the variable names do not conflict
with each other (especially if the page uses more than one script). 

## VARIABLE SCOPE 

* The location where you declare a variable will affect where it can be used
within your code. If you declare it within a function, it can only be used
within that function. This is known as the variable's scope. 

## HOW MEMORY & VARIABLES WORK 

* Global variables use more memory. The browser has to remember them
for as long as the web page using them is loaded. Local variables are only
remembered during the period of time that a function is being executed. 

## Article
### 6 Reasons for Pair Programming 

> How does pair programming work ?

*While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator. The Driver is the programmer who is typing and the only one whose hands are on the keyboard. Handling the “mechanics” of coding, the Driver manages the text editor, switching files, version control, and—of course writing—code. The Navigator uses their words to guide the Driver but does not provide any direct input to the computer. The Navigator thinks about the big picture, what comes next, how an algorithm might be converted in to code, while scanning for typos or bugs. The Navigator might also utilize their computer as a second screen to look up solutions and documentation, but should not be writing any code.*

> Why pair program ?

*While learning to code, developers likely study several programming languages. Similar to a foreign language class, there are four fundamental skills that help anyone learn a new language: Listening: hearing and interpreting the vocabulary Speaking: using the correct words to communicate an idea Reading: understanding what written language intends to convey Writing: producing from scratch a meaningful* 
 
 1. Greater efficiency 

 **It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.** 

 2. Engaged collaboration 

 **When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone.** 

 3. Learning from fellow students 

 **Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of.** 

 4. Social skills 

 **Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills.** 

 5. Job interview readiness 

 **A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base**

 6. Work environment readiness 

 **Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.** 