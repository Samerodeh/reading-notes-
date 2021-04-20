# HTML 

## Chapter 7 

### Forms 

> Why Forms ?

**The best known form on the web is probably
the search box that sits right in the middle of
Google's homepage.** 

![Form Google HomePage](data:image/png;base64,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) 

> Form Controls 

**There are several types of form controls that
you can use to collect information from visitors
to your site.** 

> ADDING TEXT: 

* Text input (single-line) 

*Used for a single line of text such
as email addresses and names.* 

* Password input

*Like a single line text box but it
masks the characters entered.* 

* Text area (multi-line)\

*For longer areas of text, such as
messages and comments.*

> How Forms Work 

**A user fills in a form and then presses a button
to submit the information to the server.** 

![Form Work](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcShHMeq82gl0BXYyp1jG_rZYBaPqWzMcYc37Q&usqp=CAU) 

> Form Structure 

* (form)

*Form controls live inside a
(form) element. This element
should always carry the action
attribute and will usually have a
method and id attribute too.*

* action

*Every (form) element requires
an action attribute. Its value
is the URL for the page on the
server that will receive the
information in the form when it
is submitted.*

* method

*Forms can be sent using one of
two methods: get or post.*

" Elements write between <> " 

> Text Input 

* (input)

*The (input) element is used
to create several different form
controls. The value of the type
attribute determines what kind
of input they will be creating.* 

" Elements write between <> " 

> Text Area 

* (textarea)

*The (textarea) element
is used to create a mutli-line
text input. Unlike other input
elements this is not an empty
element. It should therefore have
an opening and a closing tag.* 

> Radio Button 

**Radio buttons allow users to pick
just one of a number of options.** 

> Checkboxes

**Checkboxes allow users to select
(and unselect) one or more
options in answer to a question.** 

> File Input Box

**If you want to allow users to
upload a file (for example an
image, video, mp3, or a PDF),
you will need to use a file input
box.** 

**type="file"
This type of input creates a
box that looks like a text input
followed by a browse button.
When the user clicks on the
browse button, a window opens
up that allows them to select a
file from their computer to be
uploaded to the website.** 

> Submit Button 

**type="submit"**

**The submit button is used to
send a form to the server.**

> HTML5: Form Validation 

**You have probably seen forms
on the web that give users
messages if the form control has
not been filled in correctly; this is
known as form validation.** 

**Traditionally, form validation
has been performed using
JavaScript (which is beyond the
scope of this book). But HTML5
is introducing validation and
leaving the work to the browser.** 

**Validation helps ensure the
user enters information in a
form that the server will be able
to understand when the form
is submitted. Validating the
contents of the form before it is
sent to the server the helps:** 

* Reduce the amount of work
the server has to do 

* Enables users to see if there
are problems with the form
faster than if validation were
performed on the server. 

## Chapter 14

### Lists, Tables & Forms 

> list-style-type 

**The list-style-type property
allows you to control the shape
or style of a bullet point (also
known as a marker).
It can be used on rules that
apply to the (ol), (ul), and (li)
elements.** 

" Elements write between <> " 

> list-style-image 

**You can specify an image to act
as a bullet point using the
list-style-image property.** 

> list-style-position 

**Lists are indented into the page
by default and the list-styleposition
property indicates
whether the marker should
appear on the inside or the
outside of the box containing the
main points.** 

> list-style 

**As with several of the other CSS
properties, there is a property
that acts as a shorthand for list
styles. It is called list-style,
and it allows you to express
the markers' style, image and
position properties in any order.** 

> Table Properties 

* width 

*to set the width of the table*

* padding 

*to set the space between the border of each table cell and its content* 

* text-transform 

*to convert the
content of the table headers to
uppercase*
 
* letter-spacing, font-size

*to add additional styling to the
content of the table headers* 

* border-top, border-bottom

*to set borders above and below
the table headers* 

* text-align 

*to align the writing
to the left of some table cells and
to the right of the others*

* background-color 

*to change
the background color of the
alternating table rows* 

* :hover 

*to highlight a table row
when a user's mouse goes over it* 

> Styling Forms 

**CSS is commonly used to
control the appearance of form
elements. This is both to make
them more attractive and to
make them more consistent
across different browsers** 

# JAVASCRIPT 

## Chapter 6

### Events 

***Scripts often respond to these events by updating the content of the web page (via the
Document Object Model) which makes the page feel more interactive.*** 

> DIFFERENT EVENT TYPES 

1. UI EVENTS 
2. KEYBOARD EVENTS 
3. MOUSE EVENTS 
4. FOCUS EVENTS 
5. MUTATION EVENTS 

> HOW EVENTS TRIGGER JAVASCRIPT CODE 

1. Select t he element node(s) you want the script to respond to.
2. Indicate which event on the selected node(s) will trigger the response.
3. State the code you want to run when the event occurs. 

> TRADITIONAL DOM EVENT HANDLERS 

**All modern browsers understand this way of creating an event handler, but you can only attach one function to each event handler.** 

> EVENT LISTENERS 

**Event listeners are a more recent approach to handling events. They can deal with more than one function at a time
but they are not supported in older browsers.** 

> USING PARAMETERS WITH EVENT HANDLERS & LISTENERS 

**Because you cannot have parentheses after the
function names in event handlers or listeners,
passing arguments requires a workaround.** 

> THE EVENT OBJECT 

**When an event occurs, the event object tells
you information about the event, and the
element it happened upon.** 

> WHICH ELEMENT DID AN EVENT OCCUR ON ?

**When calling a function, the event object's target property is the best
way to determine which element the event occurred on. But you may see
the approach below used; it relies on the this keyword.** 

* THE this KEYWORD 

*The this keyword refers to the
owner of a function.* 

