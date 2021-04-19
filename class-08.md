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