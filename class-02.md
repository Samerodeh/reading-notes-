#  HTML 

## Chapter 2 

### Text 

>1. Structural markup: 

*the elements that you can use to
describe both headings and paragraphs* 

***headings***

**HTML has six "levels" of headings:**

(h1) is used for main headings

(h2) is used for subheadings

(h3) element is used If there are further sections
under the subheadings 

*   heading tags write between <>


> example : 


- <h1>This is a Main Heading</h1>
- <h2>This is a Level 2 Heading</h2>
- <h3>This is a Level 3 Heading</h3>
- <h4>This is a Level 4 Heading</h4>
- <h5>This is a Level 5 Heading</h5>
- <h6>This is a Level 6 Heading</h6>

***Paragraph***

**To create a paragraph, surround
the words that make up the
paragraph with an opening (p)
tag and closing (/p) tag.**

* paragraph tags write between <>

> 2. Semantic markup: 

*which provides extra information; such
as where emphasis is placed in a sentence, that something
you have written is a quotation (and who said it), the
meaning of acronyms, and so on* 


***There are some text elements that are not intended to affect the
structure of your web pages, but they do add extra information to the
pages — they are known as semantic markup.*** 

1. Strong  

*The use of the (strong)
element indicates that its
content has strong importance.
For example, the words
contained in this element might
be said with strong emphasis.*

* strong tags write between <>

> example : 

"<p><strong>Beware:</strong> Pickpockets operate in
this area.</p>
<p>This toy has many small pieces and is <strong>not
suitable for children under five years old.
</strong></p>" 

2. Changes to Content 

* S tag 

*The (s) element indicates
something that is no longer
accurate or relevant (but that
should not be deleted).
Visually the content of an (s)
element will usually be displayed
with a line through the center.*  

* s tags write between <>

> example :  

<p>Laptop computer:</p>
<p><s>Was $995</s></p>
<p>Now only $375</p>

3. Auth or Details 

* (address) 

*The (address) element has
quite a specific use: to contain
contact details for the author of
the page.*

* address tags write between <>

> example : 

<address>
<p><a href="mailto:homer@example.org">
homer@example.org</a></p>
<p>742 Evergreen Terrace, Springfield.</p>
</address>

# CSS 

## Chapter 10

### Introducing CSS 

***CSS allows you to create rules that specify how the content of
an element should appear. For example, you can specify that
the background of the page.***

### CSS Associates Style rules with HTML elements:

* CSS works by associating rules with HTML elements. These rules govern
how the content of specified elements should be displayed. A CSS rule
contains two parts: a selector and a declaration. 

1. Selectors

*indicate which
element the rule applies to.
The same rule can apply to
more than one element if you
separate the element names
with commas.*

2. Declarations 

*indicate how
the elements referred to in
the selector should be styled.
Declarations are split into two
parts (a property and a value),
and are separated by a colon.*

### How Elements Are Displayed ?

* CSS declarations sit inside curly brackets and each is made up of two
parts: a property and a value, separated by a colon. You can specify
several properties in one declaration, each separated by a semi-colon.

1. Properties 

*indicate the aspects
of the element you want to
change. For example, color, font,
width, height and border.* 

2. Values 

*specify the settings
you want to use for the chosen
properties. For example, if you
want to specify a color property
then the value is the color you
want the text in these elements
to be.*

### HOW Using External CSS ?

> #### link 

**The (link) element can be used
in an HTML document to tell the
browser where to find the CSS
file used to style the page. It is an
empty element (meaning it does
not need a closing tag), and it
lives inside the <head> element.
It should use three attributes:**

> 1. href

*This specifies the path to the
CSS file (which is often placed in
a folder called css or styles).*

> 2. type

*This attribute specifies the type
of document being linked to. The
value should be text/css*.

> 3. rel 

*This specifies the relationship
between the HTML page and
the file it is linked to. The value
should be styleshee*

### HOW Usi ng Internal CSS ?

#### (style)

**You can also include CSS rules
within an HTML page by placing
them inside a (style) element,
which usually sits inside the
(head) element of the page.** 